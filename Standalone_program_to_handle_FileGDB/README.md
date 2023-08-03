# Data Pipeline GUI with Tkinter

This Python script implements a graphical user interface (GUI) using Tkinter to execute a data pipeline on GeoDataFrames. The script allows users to browse for an input file containing GeoDataFrames, specify an output file, and then execute a series of data processing steps on the GeoDataFrames. The processed GeoDataFrames are then saved to the specified output file.

![Screenshot](https://github.com/RuneTheander/GIS-In-Python/raw/main/Standalone_program_to_handle_FileGDB/Displayfil.PNG)

## Dependencies

The script requires the following Python libraries to be installed:

- `tkinter`: Provides the GUI framework for creating windows, buttons, labels, etc.
- `pandas`: Used for working with data in tabular format.
- `geopandas`: Extends pandas to support spatial data and provides geometric operations.
- `fiona`: Allows reading and writing geospatial data formats using the GDAL library.
- `threading`: Provides multi-threading support to execute tasks concurrently.
- `tqdm`: Enables displaying progress bars for data processing tasks.
- `shapely.geometry`: Provides geometric objects (Point, LineString, Polygon) for spatial operations.
- `colorama`: Used for adding colored output messages to the GUI.

## GUI Components

The GUI consists of the following components:

### Input File
An entry field and a "Browse" button to select the input file containing GeoDataFrames.

### Output File
An entry field and a "Browse" button to specify the output file where processed GeoDataFrames will be saved.

### Execute Data Pipeline
A button labeled "Execute Data Pipeline" that starts the data processing when clicked.

### Progress Bar
A progress bar and a label to display the progress of data processing.

### Output Text
A text widget to display the console output, including progress messages and any errors.

## Data Processing Steps

1. **Read Data**: The script reads the GeoDataFrames from the input file using the `fiona` and `geopandas` libraries. The progress bar updates while reading each layer of the input file.

2. **Process Data**: The script processes each GeoDataFrame to remove rows with an action 'delete'. If any objects have Z values (altitude) above 5000, the script modifies those Z values to -999.

    - For **Point** GeoDataFrames: If the Z value of a Point geometry is greater than 5000, it is updated to -999.
    - For **LineString** and **MultiLineString** GeoDataFrames: If the Z value of a coordinate in a LineString geometry is greater than 5000, the entire coordinate is updated to have a Z value of -999.
    - For **Polygon** and **MultiPolygon** GeoDataFrames: If the Z value of a coordinate in a Polygon exterior ring is greater than 5000, the entire coordinate is updated to have a Z value of -999.

3. **Save Data**: The modified GeoDataFrames are saved to the output file in OpenFileGDB format using the `geopandas` library. The progress bar updates while saving each layer to the output file.

## Execution

The user selects the input and output files using the "Browse" buttons, then clicks the "Execute Data Pipeline" button to start the data processing. The GUI provides real-time updates on the progress of reading and processing each layer. The output console displays progress messages, and any errors encountered during the execution are also shown.

Once the data pipeline is completed, the GUI allows the user to execute the pipeline again or choose different input and output files.
