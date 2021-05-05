# Image-captioning
Image captioning project 



# Unified VLP
In order to run the VLP scripts please download our finetuned VLP model from here 
https://drive.google.com/file/d/1rHYejDkI5BExUZqZUtReCL3qwt39aHrq/view?usp=sharing

Also need to download the Flickr 8k dataset from here
https://www.kaggle.com/adityajn105/flickr8k?select=captions.txt

Now, you can run sample scripts from the Luowei et Al. github 
https://github.com/LuoweiZhou/VLP

Example script for inference (Provide paths for model, json file, and images folder)

`python vlp/decode_img2txt.py \
    --model_recover_path model/model.50.bin \
    --new_segment_ids --batch_size 100 --beam_size 5 \
    --image_root archive/images --split test \
    --dataset flickr30k \
    --src_file dataset_flickr8k.json `

Note you will also need to initialize the pytorch resnet 101 model in the VLP/decode_img2txt.py file. 
https://pytorch.org/hub/pytorch_vision_resnet/

Uncomment the line at 172 and replace with this 
`cnn = torch.hub.load('pytorch/vision:v0.9.0', 'resnet101', pretrained=True)`
also Uncomment line 178, 185
