# ForecastingEvents
Does it Happen and When - Binary Classification and Regression.

### Scenario

A retail shop has deployed electronic tags on each of their items (aka assets) and installed infrastructure at the receiving area of their store. The recieving area is where trailers pull up to the dock door to unload assets. 

__Deployment Setup__
+ Each item has 1 pixel attached
+ Two zones are installed with "bridges", with multiple bridges installed at each zone to maximize coverage.
    + `GMReceiving`
        + the bridges installed next to the receiving door
    + `FastSorter`
        + fast sorter machine located inside the store and close to the trailer receiving door
        + items get unloaded one by one into the store through fast sorter machine

__How data are generated__
+ The pixels are energized by hardware called “bridges”. 
+ Once energized, the pixels transmit data back to the "bridges".
+ Data is then transmitted to the "gateway".
+ "Gateways" send the data onto the "cloud".  

You have a limited dataset with the raw data from some pixels, along with labels for which pallet the pixels ended up on. You also have bridge and gateway ID’s where the signals were received.

### Task
Using the provided Train and Validation datasets, please create a model or heuristics to **determine which and when each item gets unloaded from the trailer parked at the receiving door of the store**

+ Develop the model/heuristic based on the train data and evaluate on the validation data. 

+ Upon design completion, prepare the final code such that it can run on a hidden test set, which will follow the exact same format as the validation set, except without the "unload_timestamp" column. If you generate a trained model, please ensure you include the model weights.

The prediction output should be a predictions dataframe that contains 3 columns: 
+ "pixel_id"
+ "unload_timestamp_pred"
+ "unload_pred" 
If `unload_pred` is 0 (not unloaded), the `unload_timestamp_pred` should be an empty string.
If `unload_pred` is 1 (unloaded), the `unload_timestamp_pred` should contain a 13-digit timestamp.

The final section of this notebook has cells that should not be modified.  This is designed to evaluate your model/heuristic performance on the hidden test set.
