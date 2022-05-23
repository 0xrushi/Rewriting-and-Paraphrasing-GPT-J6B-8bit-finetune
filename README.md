## Fine-tuning 6-Billion GPT-J in colab with LoRA and 8-bit compression 
This notebook is a simple example for fine-tuning [GPT-J-6B](https://huggingface.co/EleutherAI/gpt-j-6B) with limited memory. 

A detailed explanation of how it works can be found in [this model card](https://huggingface.co/hivemind/gpt-j-6B-8bit). 

You can also finetune [GPT-Neo-2.7B](https://huggingface.co/gustavecortal/gpt-neo-2.7B-8bit), or use same concept in any new model.

**Huge thanks to Hivemind and Gustave Cortal!**

## Task: Rewriting and Paraphrasing

Paraphrasing/Rewriting is about generating a new content that keeps the same sense as the original content, but with different words.

Performing simple paraphrasing by simply changing a couple of words is one thing, but generating advanced paraphrasing that completely changes the structure of sentences and the vocabulary used is another beast! Modern models like GPT-3, GPT-J, and GPT-NeoX, now make it possible to easily create advanced and complex paraphrasing that properly keeps the main sense while using a different wording.

We do have few-shot learning strategies where we provide the AI only a few samples, and enhance the results without having to train a specialized AI.

Few-shot learning isn't always enough (for example if your paraphrasing relies on very specific content, bound to your industry only). In that situation, fine-tuning (training) GPT-J with your own data is the best option.

**Concerns with GPT-3**:
- Not open source!, to use GPT-3 for paraphrasing will only be free till some paragraphs

**Concerns with GPTJ-6B/ GPT-Neo**
- Open source but too resource heavy!
- Once you have a good bundled dataset, you can rent a cloud server and nicely finetune on these models

**Why GPT-J in colab with LoRA and 8-bit compression** ?
- You can use a modified version of GPTJ to train on free clouds like colab or kaggle with no server cost!


**Usecase:**
- Content Creation
- Product description
- Ad creation
- Research Writing


## Dataset: [PAWS](https://github.com/google-research-datasets/paws)- Paraphrase Adversaries from Word Scrambling

This dataset contains 108,463 human-labeled and 656k noisily labeled pairs that feature the importance of modeling structure, context, and word order information for the problem of paraphrase identification. 

**PAWS-Wiki Labeled (Final)**: containing pairs that are generated from both word swapping and back translation methods from Wikipedia pages. All pairs have human judgements on both paraphrasing and fluency and they are split into Train/Dev/Test sections.

Though there is plenty of data, due to time and constraints, the model was finetuned on only 5000 sentences from train.tsv.  
