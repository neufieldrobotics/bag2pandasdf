# bag2pandasdf
Convert rosbags to pandas dataframes for easy data manipulation and plotting

* Takes a rosbag file and converts it to a pndas dataframe pickle file based on settings specified in a Dictionary and a yaml config file.
  - Dictonary: The dicionary file specified which variables from each message type should be converted to a dataframe columns.
    eg `sensor_msgs/NavSatFix: t.to_sec(), m.latitude, m.longitude, m.altitude`
    See config/bag2mat_dic.yaml for full example.
  - Configuration: This file specified which topic names should be transferred to dataframes and under which variable name.
    A list of `-[topic name, message type, name for variable in matfile]`
    See config/bag2mat_config.yaml for full example.
* Currently needs the following packages:
  - rosbag
  - pandas
  - numpy
  - pyyaml
  - tqdm

* Usage
```
usage: bag2pandasdf.py [-h] -i INPUT_BAGFILE [-o OUTPUT_DIR] [-c CONFIG_FILE]
                       [-d DICTIONARY]

Convert ROSBAG to pandas dataframe pkl file.

A simple script that can converts rosmessages in a rossbag to pandas dataframes in a .pkl file.                                  
Define the translation of each message type in a dictionary file and use a config file to specify all the topics to be converted..

arguments:
  -i INPUT_BAGFILE, --input_bagfile INPUT_BAGFILE
                        Input rosbag file to input
                        
optional arguments:
  -h, --help            show this help message and exit
  -o OUTPUT_DIR, --output_dir OUTPUT_DIR
                        Output dir for pkl file
  -c CONFIG_FILE, --config_file CONFIG_FILE
                        Yaml file which specifies topic names to convert
  -d DICTIONARY, --dictionary DICTIONARY
                        Dictionary file which specifies how to read the topic
```
