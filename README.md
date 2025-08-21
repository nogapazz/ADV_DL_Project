## Important Notes About Running in Google Colab

Google Colab runtimes disconnect frequently. This means that:
- All **local variables are lost** after a disconnect.
- The notebook can sometimes **collapse in the middle of a run**.
- If you try to run cells that depend on lost variables (for example, saving a model after a disconnect), you will get errors.

Because of this, in **Part B**:
- Some cells look redundant. This happened because after a disconnect we had to **re-define objects** or **re-load from Drive** multiple times.
- Example: we trained a model, saved it to Drive, then Colab disconnected. When re-running only the "save" cell, the model variable no longer existed, causing errors.

⚠️ Important:
- If you are not going to run the training processes, do not run the saving cells afterwards — those cells depend on variables defined during training and will error out if run independently.
- This notebook is designed for **Google Colab**, please run it in google colab (we tried not to, but it caused us a lot of errors and fixes which can be seen unfortunately in the notebook).

### Checkpoints (must be placed in Google Drive)

All fine-tuned checkpoints are already stored here:  
👉 [Shared Drive Folder](https://drive.google.com/drive/folders/1JgW6f8UBvL4df6QoXTAgsjZqP03H58Vf?usp=sharing)

#### How to run
1. Create a folder: `MyDrive/ADV_DL/` in your own Google Drive.  
2. Copy the shared contents into `MyDrive/ADV_DL/` (make sure the path is the same as in the codes)
3. Open "Google Colab" in the same chrome account of the drive where you pasted the ADV_DL directory to.
4. Open in Colab: run **Part 1.ipynb** (EDA + preprocessing).  
5. Then open in Colab: run **Part 2.ipynb** (fine-tuning, tuning, compression, evaluation).


### Running Environment
- This notebook is designed for **Google Colab**, please run it in google colab.



 ## Part A notebook — EDA & preprocessing (Part 1.ipynb)
   - It loads the Kaggle COVID‑19 NLP dataset (reference only) and produces the working files: bertweet_train.xls, bertweet_test.xls, distilbert_train.xls, distilbert_test.xls and length_stats.json.
   - Key decisions:
      - Collapse 5 labels → 3 labels {negative, neutral, positive}.
      - Tweet‑aware cleaning: preprocess hashtags, normalize @user and URLs, strip noise only where helpful.
      - Export basic length/token stats for both tokenizers.

 ## Part B notebook — fine‑tuning, tuning, compression, evaluation (Part 2.ipynb)
   - The notebook supports both Hugging Face Trainer and a full‑code loop for each model, plus Optuna tuning and 3 compression methods.
   - Primary weights live under hf_best/* (HF version from exercise 5) and final_models/* ("full code" version from exercise 4)
   - Two models compared: vinai/bertweet‑base and distilbert‑base‑uncased.
   - Tokenizers are reloaded from `hf_best/<model>`

   

   - 
### Notes and Assumptions
- All comparisons were made on **validation data**. We did not re-run the same comparisons on the test set.  
- After completing the comparisons on evaluation data, we did run the models once more on the test set to confirm that inference works properly.
- We dont have a code to address the emojis cause we checked and saw that there are no emojis in the data set.
- We tried to make the notebook pretty but also wanted to keep everything documented as you requested.

 
