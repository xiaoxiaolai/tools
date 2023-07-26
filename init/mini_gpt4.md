
git lfs install
git clone https://huggingface.co/lmsys/vicuna-13b-delta-v0  # more powerful, need at least 24G gpu memory
# or
git clone https://huggingface.co/lmsys/vicuna-7b-delta-v0  # smaller, need 12G gpu memory


python -m fastchat.model.apply_delta --base ../llama-7b-hf/  --target ../MiniGPT-4/vicuna_weights/  --delta ../vicuna-7b-delta-v0/



https://devpress.csdn.net/aitech/6465bec7ed6c8c2acf6a68fb.html