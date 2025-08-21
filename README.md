## Important Notes About Running in Google Colab

Google Colab runtimes disconnect frequently. This means that:
- All **local variables are lost** after a disconnect.
- The notebook can sometimes **collapse in the middle of a run**.
- If you try to run cells that depend on lost variables (for example, saving a model after a disconnect), you will get errors.

Because of this, in **Part B**:
- Some cells look redundant. This happened because after a disconnect we had to **re-define objects** or **re-load from Drive** multiple times.
- Example: we trained a model, saved it to Drive, then Colab disconnected. When re-running only the "save" cell, the model variable no longer existed, causing errors.

⚠️ Important:
If you are not going to run the training processes, do not run the saving cells afterwards — those cells depend on variables defined during training and will error out if run independently.

### Checkpoints (must be placed in Google Drive)

All fine-tuned checkpoints are already stored here:  
👉 [Shared Drive Folder](https://drive.google.com/drive/folders/1JgW6f8UBvL4df6QoXTAgsjZqP03H58Vf?usp=sharing)

#### One-time Setup in Your Google Drive
1. Create a folder: `MyDrive/ADV_DL/` in your own Google Drive.  
2. Copy the shared contents into `MyDrive/ADV_DL/`.

### Running Environment
- This notebook is designed for **Google Colab**, please run it in google colab.
 
### Notes and Assumptions

- All comparisons between models (DistilBERT, BERTweet, quantized, pruned, etc.) were made on the evaluation results (validation data).
- We did not re-run the same comparisons on the test set. 
However, after completing the comparisons on evaluation data, we did run the models once more on the test set to confirm that inference works properly.

 
### Drive Directories Instructions

