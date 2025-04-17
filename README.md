# SimpleR1-Reproduction


reproducing DeepSeek R1 Zero 

## Setup
Create a virtual environment and install dependencies with 
```bash
pip install -r requirements.txt
```


For a eight GPU setup, start vLLM first.

```bash
CUDA_VISIBLE_DEVICES=7 trl vllm-serve --model Qwen/Qwen2.5-1.5B
```

Then run training with

```bash
accelerate launch --config_file configs/deepspeed/zero3.yaml --num_processes 7 train.py
```

## Evaluation
Follow instructions in [`eval/README.md`](eval/README.md).

## Acknowledegments

[simpleRL-Zoo](https://github.com/hkust-nlp/simpleRL-reason)

[Qwen2.5 Math Evaluation](https://github.com/QwenLM/Qwen2.5-Math)

[smolR1](https://github.com/rasdani/smolR1)
