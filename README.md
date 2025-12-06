# Exgralora

## 1. Medical VQA Evaluation

```bash
# supports VQA-RAD, SLAKE, PATH-VQA

# change the following
# --model-name: Path to load the model from finetuning stage
# --answers-file: file to store the result (i.e the answers to the medical question)
python exgra_med/llava/eval/run_med_datasets_eval_batch.py \
--num-chunks 2 \
--model-name \<output_vqa_rad_checkpoint\> \
--mm_dense_connector_type none \
--num_l 6 \
--question-file ./data_RAD/test_w_options_new.json \
--image-folder ./data_RAD/images \
--answers-file \<answers_file\>

#change the following
#--pred: same as --answers-file above
# the metrics (recall and accuracy) are saved as a text file in the same place, with the same name as --pred. 
#E.g: if --pred is ans-opt-new-3.jsonl, then metrics are saved in ans-opt-new-3.txt
python exgra_med/llava/eval/run_eval.py \
--gt ./data_RAD/test_w_options_new.json \
--pred \<answers_file\> \
--candidate ./data_RAD/candidate.json
```
