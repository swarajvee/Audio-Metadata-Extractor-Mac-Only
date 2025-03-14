# Audio Metadata Extractor

## Description
This script extracts metadata from audio files using `afinfo` and saves the data into an Excel file. It processes various attributes like file path, artist, album, track number, duration, sample rate, bit depth, and loudness parameters.

### "I have written this script with an intension for analysing Loudness information of different songs"

## Features
- Extracts metadata from audio files using `afinfo`
- Parses metadata including file type, track number, sample rate, bit depth, and loudness info
- Saves extracted data into an Excel sheet
- Organizes output files into structured directories

## Requirements
- Python 3.x
- `openpyxl` for Excel file handling
- `numpy` for data handling
- `glob` for file path applications

## Installation
1. Open terminal in desired location
2. Download and change directory
```bash
git clone git@github.com:swarajvee/Audio-Metadata-Extractor-Mac-Only.git
cd Audio-Metadata-Extractor-Mac-Only
```
3. Install required python packages
```bash
pip install -r requirements.txt
```

## Usage
1. Place the downloaded tracks under one directory (eg: directory with the name of the playlist).
2. Usually the download location for Apple Music will be under ```/Users/yourusername/Music/Music/Media.localized/Apple Music```
3. Run the script with:
```bash
python PlaylistLoudnessAnalyzer2_5_(Mac_only).py
```
4. Upload the path of the directory you have created in the script when prompted
5. The extracted metadata will be saved in an `Analysis` directory, structured by artist and date.

## Functions
### `afinfo(file)`
Runs `afinfo` on the given file and returns the metadata output.

### `parsed_data(af_out)`
Parses the `afinfo` output and extracts relevant metadata.

### `Excel_Maker(metadata)`
Creates an Excel file from the extracted metadata and organizes it into a structured directory.

## Output
The script generates an 'Analysis' folder and a sub folder with the name of music directory and a sub-sub folder with current date as its folder name and an Excel file named `{Music_Directory_Name}_{Date}.xlsx` inside that directory.

## Example Output
An example row in the output Excel file:
| Sl.NO | Artist | Track | Album/Single/EP | Duration (Min) | Sample Rate | Source Bit Depth | Main AA EBU Max Momentary Loudness | Main AA EBU Top Of Loudness Range | Main AA ITU Sample Peak | Main AA ITU True Peak | Main AA EBU Max Short Term Loudness | Main AA EBU Loudness Range | Main AA ITU Loudness | Album AA EBU Max Momentary Loudness | Album AA EBU Top Of Loudness Range | Album AA ITU Sample Peak | Album AA ITU True Peak | Album AA EBU Max Short Term Loudness | Album AA EBU Loudness Range | Album AA ITU Loudness | SC Ave Perceived Power Coeff | SC Max Perceived Power Coeff | SC Peak Amplitude Msec | SC Max Perceived Power Msec | SC Peak Amplitude | Sound Check Volume Normalization Gain |
|------|--------|-------|----------------|---------------|-------------|----------------|-----------------------------------|--------------------------------|------------------|----------------|-----------------------------------|----------------------------|----------------|-----------------------------------|--------------------------------|------------------|----------------|-----------------------------------|----------------------------|----------------|-----------------------------|-----------------------------|---------------------|----------------------|------------------|--------------------------------------|
| 1 | Ado | 01 Show | Show - Single | 3.16 | 44100 Hz | 16 bit | 0.25 | -1.75 | 0 | 1.9375 | -1.25 | 4.75 | -3.75 | 0.25 | -1.75 | 0 | 1.9375 | -1.25 | 4.75 | -3.75 | "21737 22205" | "96187 116789" | "627 395" | "183298 98522" | "32768 32768" | -12.25 dB |

## License
This project is open-source and available for modification.

## Notes
- There will be a `info.txt` file which can provide explanation to some of the Loudness parameters
- The script is tested in m4p files in mac os Ventura, but can be modified if ```afinfo "path/to/song.extension"``` can give any song metadata
- Ensure `afinfo` is available in your system's PATH.

## Reference 
- [Apple Digital Masters: Music as the Artist and Sound Engineer Intended](https://www.apple.com/apple-music/apple-digital-masters/docs/apple-digital-masters.pdf)
- [Afinfo](https://ss64.com/mac/afinfo.html)

