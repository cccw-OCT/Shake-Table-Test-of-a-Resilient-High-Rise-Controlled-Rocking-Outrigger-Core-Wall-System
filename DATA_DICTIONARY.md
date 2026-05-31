# Trial-1 Data Dictionary

This document defines the current dataset organization and the metadata fields
recommended for long-term use.

## Directory Categories

| Directory | Category | Description |
|---|---|---|
| `1 - Design/` | design | Design overview, IFC/reference documents, and structural layout files. |
| `2 - Construction/` | construction | Assembly and construction documentation. |
| `3 - Damper/` | damper | Damper information grouped by damper type and location. |
| `4 - Instrumentation/` | instrumentation | Channel list, instrumentation drawing, and sensor/as-built photos. |
| `5 - Test/` | test | Raw test data, sequence records, ground motions, photos, and videos. |

## Raw Data Naming

Raw synchronized data files currently use:

```text
5 - Test/Raw data/RawDataA<case_id>_Sync.xlsx
```

Recommended interpretation:

| Field | Meaning |
|---|---|
| `RawData` | Raw experimental response data. |
| `A<case_id>` | Test case identifier. The case mapping should be checked against the sequence file. |
| `Sync` | Synchronized data export. |
| `.xlsx` | Spreadsheet format. |

## Recommended Case Index Fields

Create or maintain a case index with these columns:

```text
case_id
case_name
loading_type
ground_motion
direction
intensity_level
run_date
raw_data_file
photo_folder
video_folder
notes
```

## Recommended Channel Metadata Fields

The instrumentation channel list should define or be accompanied by these
fields:

```text
channel_id
channel_name
sensor_type
measured_quantity
unit
location
axis_or_direction
positive_sign_convention
sampling_rate
calibration_factor
raw_data_column
notes
```

## Recommended Media Metadata Fields

For photos and videos, maintain an index with:

```text
file_path
case_id
media_type
camera_or_view
component
test_stage
start_time
end_time
description
```

## File Manifest

`MANIFEST.csv` is a generated file inventory. Its columns are:

| Column | Description |
|---|---|
| `path` | Repository-relative file path. |
| `top_category` | First-level directory. |
| `extension` | File extension. |
| `size_bytes` | Current worktree file size in bytes. |
| `git_lfs` | `true` if the file is tracked by Git LFS. |
| `last_write_time` | Last modified time on the source machine when the manifest was generated. |

## Git LFS

Many dataset files are stored through Git LFS. Users must run:

```powershell
git lfs install
git lfs pull
```

after cloning the repository.

