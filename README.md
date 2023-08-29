# GPT-3.5_Fine-Tune
Fine-Tune GPT-3.5-turbo 

You can easily fine-tune your own datas for fine-tune on gpt-3.5-turbo.

I used version for pyhton is 3.10 and with anaconda envs

'''conda
conda create -n your_envs_name python=3.10
'''

cd ./././ 

Install the following dependencies

pip install openai

(recommand to install new envs for latest version of openai)

Step 1

Make jsonl files for training and validation

Example for training

{"messages": [{"role": "system", "content": "당신은 건설 하자 전문가입니다."}, {"role": "user", "content": "벽에 균열이 생겼어요. 어떻게 해야 하나요?"}, {"role": "assistant", "content": "구조적인 문제일 수 있으니 전문 엔지니어와 상담하세요."}]}
{"messages": [{"role": "system", "content": "당신은 건설 하자 전문가입니다."}, {"role": "user", "content": "도배가 찢어졌어요. 어떻게 해야 하나요?"}, {"role": "assistant", "content": "찢어진 부분만 손보는 것보다 전체 면을 갈아엎는 것이 좋습니다. 전문가에게 도움을 청하세요."}]}
{"messages": [{"role": "system", "content": "당신은 건설 하자 전문가입니다."}, {"role": "user", "content": "벽지에 오염이 생겼어요. 어떻게 해야 하나요?"}, {"role": "assistant", "content": "오염된 부분만 손보는 것보다 전체 면을 갈아엎는 것이 좋습니다. 전문가에게 도움을 청하세요."}]}

(OpenAI recomend to make training data more than 10 and best for more than 50 to 100 lines for like above.

Example for validation

As you knonw for validation data, you can choose how much you will make for validation data (i made 50% of training data)

format is just like the example of training.


Step 2

Refer to 3.5turbo_finetune.ipynb

* You must have your own OPENAI_API_KEY and set your preferred set (os.environ or just put an openai.api-key in notebook (recommnad when you do this job on your own workstation)
* Openai highly recommand for this fine-tune job for specific domain (Our main domain is the construction interior and solved defective in finished materials so, i put every prompt on jsonl about our domain)

