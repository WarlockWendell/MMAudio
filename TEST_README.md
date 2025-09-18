#### setup
```bash
conda create -n mmaudio python=3.12
conda activate mmaudio

pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118 --upgrade

pip install -e .

pip install matplotlib
```

在 `config/eval_data/base.yaml` 中修改 csv 的位置
在 `config/eval_config.yaml` 中修改 `duration` 和 `batchsize` 

#### run
```bash
torchrun --standalone --nproc_per_node=1 batch_eval.py duration_s=4 dataset=javisbench model=small_16k
```
模型可以选择：`large_44k`, `large_44k_v2`, `medium_44k`, `smal_16k`, `small_44k`