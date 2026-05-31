# Trial-1 Experimental Database

This repository stores the Trial-1 high-rise structural experiment database,
including design documents, construction records, damper information,
instrumentation files, raw synchronized test data, ground motions, photos, and
videos.

Large binary files are stored with Git LFS. A normal Git clone without LFS will
only download small pointer files for many spreadsheets, documents, photos, and
videos.

## Download

Install Git LFS before downloading the full dataset:

```powershell
git lfs install
git clone https://github.com/cccw-OCT/Trial-1.git
cd Trial-1
git lfs pull
```

Check that LFS files have been downloaded:

```powershell
git lfs ls-files
git status -sb
```

If files such as `.xlsx`, `.docx`, `.JPG`, or `.mp4` are only about 130 bytes,
they are still Git LFS pointer files. Run:

```powershell
git lfs pull
git lfs checkout
```

## Repository Layout

```text
1 - Design/
  Design overview and IFC/reference drawings.

2 - Construction/
  Assembly plans, component documents, construction summaries, and construction
  media.

3 - Damper/
  Damper information grouped by damper type and location.

4 - Instrumentation/
  Instrumentation channel list, drawings, and instrumentation photos.

5 - Test/
  Raw synchronized test data, test sequences, ground motions, photos, and
  videos.
```

## Key Files

```text
4 - Instrumentation/Instrumentation channel list_final.xlsx
5 - Test/Raw data/RawDataA*_Sync.xlsx
5 - Test/Sequence & Ground motions/
5 - Test/Media/
```

## Recommended Reading Order

1. Start with `1 - Design/` to understand the specimen and structural layout.
2. Use `4 - Instrumentation/Instrumentation channel list_final.xlsx` to map
   measured channels to physical locations and units.
3. Use `5 - Test/Sequence & Ground motions/` to map case numbers to the loading
   sequence and ground motions.
4. Use `5 - Test/Raw data/RawDataA*_Sync.xlsx` for synchronized response data.
5. Use `5 - Test/Media/` for visual documentation of each test stage or case.

## Data Notes

- Raw data files use the pattern `RawDataA<case_id>_Sync.xlsx`.
- Photos and videos are large files managed by Git LFS.
- File-level metadata is summarized in `MANIFEST.csv`.
- Field definitions and recommended metadata conventions are described in
  `DATA_DICTIONARY.md`.

## Citation And Access

See `ACCESS.md` for recommended citation, access, and redistribution notes.

