# Local Retrieval Augmented Generation Demo

This is a demo showing how to set up a fully local LLM + RAG (especially if you're running on CPU only). Although CPU only is far from practical for a real-world use case it is very useful for local testing, development and training. This demo runs on an i7 CPU with 16G RAM. I used a 7b model here but the same setup can run a 16b. 

# Setup
## Libraries
The main libraries are llama-index, llama-cpp-python (python wrapper for llama.cpp) and huggingface transformers.


## Models
You will need to download the weights for your LLM of choice, e.g. llama2. For local inference (and particularly for CPU only inference) the Q4_K_M.gguf variants are generally good as a balance of size and quality. 


Here this file should live in ./models e.g. "./models/llama-2-7b/llama-2-7b-chat.Q4_K_M.gguf"

## Data
The reason we're using RAG is because we have some contextual information we want to provide to the LLM in the query. Therefore we need this contextual information saved somewhere too. For the sake of a quick demo we can generate some basic documents (definitions of human diseases) in the notebook provided. This sample data comes from the [Human Disease Ontology](https://disease-ontology.org/) and the raw data is available in their [DO github](https://github.com/DiseaseOntology/HumanDiseaseOntology/blob/main/src/ontology/HumanDO.json).

Here this data should live in ./data