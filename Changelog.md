# 7/28 Changelog:
- Undo SQL change for the sake of stability, uses csv now
- Merging checkpoints bug has been resolved

# 7/26 Changelog:
- Fixed the cli inferencing traceback.
- SQL Databases implemented for formanting training stop.
- Gradio browser tab renamed to `Mangio-RVC-Web 💻`.
- Rudimentary functions from `infer-web.py` removed.
- Formanting now accepts any audio format, as long as it is supported by FFmpeg.

# 7/25 Changelog:
- Better MacOS installation script. For inference, all that needs to be done is running the `run.sh` from the extracted zip folder, where it will install Python 3.8, Homebrew, and other dependencies for you automatically. M1 Macs are natively supported for GPU acceleration, and training should work if you choose to download the pretrained models.

# 7/23 Changelog:
- Fp16 detection now works how it did before the last RVC beta; no more training slowdowns compared to how it was before then
- Logging on TensorBoard is now done per epoch. It logs every X steps in an epoch; therefore each point on the graph is now represented per-epoch.
- Updated UI to include placeholders.
- Certain sliders now appear only when needed.
- Step 2b (feature extract) is hidden if pitch guidance is disabled.
- Unnecessary radios have been replaced with checkboxes.

# 7/22 Changelog:
- Experimental Formant Shift using StftPitchShift(tried using praat with praatio but to no avail)
- Added `Stop Training` button when training, no need to restart RVC every time you want to stop the training of a model!
- Auto-detect Index path for models selected + Auto-detect paths, no more default values like this: `E:\codes\py39\vits_vc_gpu_train\logs\mi-test-1key\total_fea.npy`, We're getting Root Dir and subfolders using 
```python 
os.path.abspath(os.getcwd())
``` 
- Audio files dropdown by autodetecting files in `/audios/` folder 
- More stable version of Gradio(3.34.0) with support of Themes
- Removed `One Click Training` button in `Training` Tab, since it was glitchy and has confused a lot of users. 
- Changed default training settings to be more optimal for newer users. 
- Auto-open TensorBoard localhost URL when `tensor-launch.py` is executed 
- RMVPE implemented in both inferencing and training
