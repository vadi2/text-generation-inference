# Create endpoint

```shell
docker build . -t db4c2190dd824d1f950f5d1555fbadf0.azurecr.io/text-generation-inference:0.3.7
docker push db4c2190dd824d1f950f5d1555fbadf0.azurecr.io/text-generation-inference:0.3.7

# Not needed anymore => model weights are already present in the blob storage
#az ml model create -f model.yaml -g HuggingFace-BLOOM-ModelPage -w HuggingFace 
az ml online-endpoint create -f endpoint.yaml -g HuggingFace-BLOOM-ModelPage -w HuggingFace
az ml online-deployment create -f deployment.yaml -g HuggingFace-BLOOM-ModelPage -w HuggingFace
```

# Update endpoint

```shell
az ml online-deployment update -f deployment.yaml -g HuggingFace-BLOOM-ModelPage -w HuggingFace
```