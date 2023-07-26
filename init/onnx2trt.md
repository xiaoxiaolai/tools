```shell
python scripts/onnx2trt.py --img_pt2onnx --sam_checkpoint ../sam/model/sam_vit_h_4b8939.pth --model_type default

python -m onnxoptimizer ./embedding_onnx/sam_default_embedding.onnx ./embedding_onnx/sam_default_embedding_sim.onnx

trtexec --onnx=weights/sam_default_prompt_mask.onnx --workspace=4096 --shapes=image_embeddings:1x256x64x64,point_coords:1x1x2,point_labels:1x1,mask_input:1x1x256x256,has_mask_input:1 --minShapes=image_embeddings:1x256x64x64,point_coords:1x1x2,point_labels:1x1,mask_input:1x1x256x256,has_mask_input:1 --optShapes=image_embeddings:1x256x64x64,point_coords:1x10x2,point_labels:1x10,mask_input:1x1x256x256,has_mask_input:1 --maxShapes=image_embeddings:1x256x64x64,point_coords:1x20x2,point_labels:1x20,mask_input:1x1x256x256,has_mask_input:1 --saveEngine=weights/sam_default_prompt_mask.engine
```


pycuda==2020.1