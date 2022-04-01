# ground_truth_trajectories

Stored in `ground_truth_trajectories` collection under `trajectories` database in MongoDB.

## Description

Overview of `ground_truth_trajectories`

| Property               | Descrpition   |
| ---------------------- | ------------- |
| Simulation Software    | TransModeler  |
| Simulation Duration    | 89 minutes    |
| Size                   | 10.813 GB     |
| x_range                | 20,753 meters |
| Number of trajectories | 24747         |
| Number of lanes        | 4             |

## Schema

The Data schema for this trajectory

| Field Name           | Description                                                                                                                                                                          | Type              | Examples                     |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- | ---------------------------- |
| db_write_timestamp   | Timestamp at which the raw trajectory fragment iwritten to the database                                                                                                              | double            | [1000000.001]                |
| configuration_ID     | A unique ID that identifies what configuration was run. It links to a metadata document that defines all the settings that were used system-wide to generate this data               | int               | [1, 2, 3]                    |
| vehicle_id           | integer unique to each tracked vehicle per tracker instance assigned during stitching                                                                                                | int               | [457, 0]                     |
| fragment_ids         | array of indices pointing to fragment IDs associated to current vehicle ID                                                                                                           | Array of integers | [34,66,3]                    |
| coarse_vehicle_class | Vehicle class number                                                                                                                                                                 | int               | [4]                          |
| fine_vehicle_class   | Vehicle fine class number                                                                                                                                                            | int               | [6]                          |
| timestamp            | Corrected timestamp. This timestamp may be corrected to reduce timestamp errors.                                                                                                     | Array of double   | [1000000.001]                |
| first_timestamp      | Min timestamp from all timestamps in the trajectory fragment                                                                                                                         | double            | [1000000.001]                |
| last_timestamp       | Max timestamp from all timestamps in the trajectory fragment                                                                                                                         | double            | [1000002.001]                |
| x_position           | array of back-center x position along the road segment in feet. The position x=0 occurs at the start of the road segment.                                                            | Array of float    | [[10.1,10.2,10.3,10.4,10.5]] |
| y_position           | array of back-center y position across the road segment in feet. y=0 is located at the left yellow line, i.e., the left-most edge of the left-most lane of travel in each direction. | Array of float    | [[10.1,10.2,10.3,10.4,10.5]] |
| road_segment_id      | Unique road segment ID. This differentiates the mainline from entrance ramps and exit ramps, which get distinct road segment IDs.                                                    | Array of int      | [[1,2,3]]                    |
| starting_x           | The first x_position in the fragment.                                                                                                                                                | float             | [357.2]                      |
| ending_x             | the last x_position in the fragment                                                                                                                                                  | float             | [2357.2]                     |
| length               | vehicle length in feet                                                                                                                                                               | float             | [17.6]                       |
| width                | vehicle width in feet                                                                                                                                                                | float             | [6.6]                        |
| height               | vehicle height in feet                                                                                                                                                               | float             | [6.6]                        |
| direction            | -1 if westbound, 1 if eastbound                                                                                                                                                      | int               | [1,-1]                       |
