# LUFFY Development Repository

> 🚧 **Development Branch** - This is the main development repository for LUFFY (Learning to Reason Under Off‑Policy Guidance)

## About LUFFY

LUFFY is a reinforcement learning framework that bridges the gap between zero-RL and imitation learning by incorporating off-policy reasoning traces into the training process. This repository contains the core implementation and development work.

## 🔧 Development Status

This repository is under active development. Many features are currently being implemented or need refactoring.

## 🚀 Quick Start

⚠️ **Note**: This development version has incomplete implementations. Many features are marked as TODO and need to be completed before production use.

```bash
# Clone the repository
git clone <repository-url>
cd LUFFY

# Install dependencies
pip install -r luffy/requirements.txt

# Note: Some functionality is incomplete - check TODO list below for details
```

## 📁 Repository Structure

```
LUFFY/
├── luffy/                 # Core framework
│   ├── deepscaler/        # Scaling utilities (⚠️ API integration needed)
│   ├── verl/              # RL training components (⚠️ Some features incomplete)
│   └── ...
├── data/                  # Training data and scripts
├── eval_scripts/          # Evaluation utilities
├── exp_scripts/           # Experiment scripts
└── README.md              # This file
```

## ⚠️ Development Notes

- This is a **development version** with incomplete implementations
- Many functions contain TODO markers indicating pending work
- API integrations (OpenAI, Gemini) are currently placeholder implementations
- FSDP and distributed training features need completion


### 🔴 High Priority TODOs

- **API Integration**: OpenAI and Gemini API implementations need completion
- **Reward System**: Parallel processing and validation for reward computation  
- **FSDP Training**: Model loading and distributed training setup
- **Data Processing**: Batch dimension operations and tensor reshaping

### 📝 Complete TODO List

- [ ] **luffy/deepscaler/utils.py:45** - Add logging for API calls and errors
- [ ] **luffy/deepscaler/utils.py:46** - Support batch processing for multiple prompts
- [ ] **luffy/deepscaler/utils.py:47** - Add timeout configuration for API calls
- [ ] **luffy/deepscaler/utils.py:107** - Implement Vertex AI initialization and authentication
- [ ] **luffy/deepscaler/utils.py:108** - Configure safety settings for content generation
- [ ] **luffy/deepscaler/utils.py:109** - Set up GenerativeModel with proper system instructions
- [ ] **luffy/deepscaler/utils.py:110** - Implement retry logic with exponential backoff
- [ ] **luffy/deepscaler/utils.py:111** - Add comprehensive error handling for API access issues
- [ ] **luffy/deepscaler/utils.py:112** - Handle rate limiting and quota management
- [ ] **luffy/deepscaler/utils.py:113** - Implement response validation and text extraction
- [ ] **luffy/deepscaler/utils.py:114** - Add support for different generation configurations
- [ ] **luffy/test.py:1590** - add smaller page sizes when https://github.com/Dao-AILab/flash-attention/pull/824 is merged
- [ ] **luffy/verl/examples/split_placement/split_monkey_patch.py:141** - make a canonical logger that supports various backend
- [ ] **luffy/verl/tests/e2e/check_results.py:21** - this function needs error handling
- [ ] **luffy/verl/tests/model/test_transformer.py:22** - (sgm): add more models for test
- [ ] **luffy/verl/tests/model/test_transformer.py:50** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/model/test_transformer.py:111** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/model/test_transformers_ulysses.py:34** - (sgm): add more models for test
- [ ] **luffy/verl/tests/model/test_transformers_ulysses.py:81** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/model/test_transformers_ulysses.py:159** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/ray/test_high_level_scheduling_api.py:25** - pass *args and **kwargs is bug prone and not very convincing
- [ ] **luffy/verl/tests/ray/test_worker_group_basics.py:43** - pass *args and **kwargs is bug prone and not very convincing
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:54** - (sgm): support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:83** - it seems that manual offload is slowly than FSDP offload
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:123** - (zhangchi.usc1992): 1. support create from random initialized model. 2. Support init with FSDP directly
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:199** - (zhangchi.usc1992, shengguangming) fix me. Current, auto_wrap_policy causes HFRollout to hang in Gemma
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:207** - add transformer policy
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:226** - add more optimizer args into config
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:252** - (sgm): support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:263** - a sharding manager that do nothing?
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:391** - here, we should return all metrics
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:517** - support DCP and save sharded checkpoints
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:90** - add other ways to estimate advantages
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:168** - support each role have individual ray_worker_group_cls,
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:293** - we have to make sure the batch size is divisible by the dp size
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:599** - make a canonical logger that supports various backend
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:637** - add response length
- [ ] **luffy/verl/verl/mix_src/mix_trainer_acc_rebatch.py:63** - we have to make sure the batch size is divisible by the dp size
- [ ] **luffy/verl/verl/mix_src/mix_trainer_acc_rebatch.py:437** - make a canonical logger that supports various backend
- [ ] **luffy/verl/verl/mix_src/mix_trainer_acc_rebatch.py:592** - check path
- [ ] **luffy/verl/verl/mix_src/mix_trainer_acc_rebatch.py:628** - from remote not implemented yet
- [ ] **luffy/verl/verl/models/llama/megatron/layers/parallel_attention.py:380** - llama does not have dropout in the config??
- [ ] **luffy/verl/verl/models/llama/megatron/layers/parallel_decoder.py:78** - add sequence parallel operator reduce_scatter here
- [ ] **luffy/verl/verl/models/llama/megatron/layers/parallel_decoder.py:86** - add sequence parallel operator all_gather here
- [ ] **luffy/verl/verl/models/llama/megatron/layers/parallel_decoder.py:90** - add sequence parallel operator reduce_scatter here
- [ ] **luffy/verl/verl/models/llama/megatron/modeling_llama_megatron.py:330** - for better performance, the sp padding should be removed at each layer. Not sure the performance gap
- [ ] **luffy/verl/verl/models/llama/megatron/modeling_llama_megatron.py:588** - for better performance, the sp padding should be removed at each layer. Not sure the performance gap
- [ ] **luffy/verl/verl/models/registry.py:21** - (sgm): HF may supported more than listed here, we should add more after testing
- [ ] **luffy/verl/verl/models/transformers/llama.py:88** - These transpose are quite inefficient but Flash Attention requires the layout [batch_size, sequence_length, num_heads, head_dim]. We would need to refactor the KV cache
- [ ] **luffy/verl/verl/protocol.py:114** - Implement batch dimension folding for efficient processing
- [ ] **luffy/verl/verl/protocol.py:115** - Add validation for batch size compatibility
- [ ] **luffy/verl/verl/protocol.py:116** - Handle edge cases where batch_size is not divisible by new_batch_size
- [ ] **luffy/verl/verl/protocol.py:117** - Optimize memory usage during tensor reshaping
- [ ] **luffy/verl/verl/protocol.py:118** - Add support for different tensor types and shapes
- [ ] **luffy/verl/verl/protocol.py:131** - Implement batch dimension unfolding functionality
- [ ] **luffy/verl/verl/protocol.py:132** - Add support for variable batch dimensions
- [ ] **luffy/verl/verl/protocol.py:133** - Optimize tensor view operations for performance
- [ ] **luffy/verl/verl/protocol.py:134** - Handle non-tensor batch data reshaping properly
- [ ] **luffy/verl/verl/protocol.py:135** - Add error handling for invalid batch dimensions
- [ ] **luffy/verl/verl/protocol.py:156** - (zhangchi.usc1992) add consistency check
- [ ] **luffy/verl/verl/protocol.py:252** - we can actually lift this restriction if needed
- [ ] **luffy/verl/verl/protocol.py:338** - (zhangchi.usc1992) whether to copy
- [ ] **luffy/verl/verl/single_controller/ray/base.py:439** - create a class with customizable name
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/arg_utils.py:64** - (shengguangming): delete the unused args
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/arg_utils.py:147** - (woosuk): Support fine-grained seeds (e.g., seed per request).
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm.py:237** - (shengguangming): maybe we can hack the autoregressive logics without only init by ourselves
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm.py:400** - support sliding window attention for long context.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm.py:453** - maybe we can use some prefix-aware cache / KV cache to reduce the memory overhead of prefix
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm.py:516** - add support for beam search
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm.py:609** - (woosuk): Profile swapping overhead and optimize if needed.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm.py:730** - (shengguangming): profile and optimize if needed
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm.py:868** - (shengguangming): for now we do not use it.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm.py:893** - (shengguangming): we may need to fix the logits position for rolled out tokens
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm.py:1084** - (woosuk): this is only for notebook demo. We don't have to support it in production.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/logits_processor.py:8** - (shengguangming): do we really need this processor? or we can just forbid the logits of specific tokens.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/model_executor.py:104** - remove it later.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/model_executor.py:105** - (woosuk): Lazily initialize the model.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/model_executor.py:167** - (woosuk): Use the model config and tokenizer to check the number
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/model_loader.py:21** - (shengguangming): may need to support other model format, e.g., DeepSpeed, Megatron
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/sampling_metadata.py:23** - (woosuk): Add more sampling parameters.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/worker.py:103** - (shengguangming): we may need a better name.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/worker.py:211** - (shengguangming): how to load weight only on one device?
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/worker.py:237** - (shengguangming): for now, we only implement the llama model. we can add more later.
- [ ] **luffy/verl/verl/trainer/rl_trainer.py:220** - we can compute the norm of gradient and log it for debugging
- [ ] **luffy/verl/verl/utils/gpu_memory_track.py:25** - (zhangchi.usc1992) not sure if we should track here
- [ ] **luffy/verl/verl/utils/timer.py:32** - (zhangchi.usc1992) implement sync timer.
- [ ] **luffy/verl/verl/workers/rollout/evaluation.py:32** - we can add more metrics
- [ ] **luffy/verl/verl/workers/rollout/hf_rollout.py:87** - (sgm): support batch generation
- [ ] **luffy/verl/verl/workers/rollout/hf_rollout.py:236** - add support for more models
- [ ] **luffy/verl/verl/workers/rollout/hf_rollout.py:279** - pad response to be the same length
- [ ] **luffy/verl/verl/workers/rollout/hf_rollout.py:335** - pad response to be the same length
- [ ] **luffy/verl/verl/workers/rollout/hf_rollout.py:362** - (sgm): check for correctness and add more test cases
- [ ] **luffy/verl/verl/workers/rollout/hf_rollout.py:375** - (sgm): add support for more models (e.g. Gemma)
- [ ] **luffy/verl/verl/workers/rollout/hf_rollout.py:411** - add response length
- [ ] **luffy/verl/verl/workers/rollout/hf_rollout.py:427** - (zhangchi.usc1992): we can build a general pad tensor function
- [ ] **luffy/verl/verl/workers/rollout/rollout_pool.py:93** - add logger
- [ ] **luffy/verl/verl/workers/rollout/rollout_pool.py:108** - add metrics
- [ ] **luffy/verl/verl/workers/rollout/vllm_rollout.py:140** - make a canonical logger that supports various backend
- [ ] **luffy/verl/verl/workers/rollout/vllm_rollout.py:192** - add support for generate_sequences (deprecated) and batched_generate
- [ ] **luffy/verl/verl/workers/rollout/vllm_rollout.py:247** - add response length
- [ ] **luffy/verl/verl/workers/rollout/vllm_rollout.py:264** - add support for generate_sequences (deprecated) and batched_generate
- [ ] **luffy/verl/verl/workers/rollout/vllm_rollout.py:303** - add response length
- [ ] **luffy/verl/verl/workers/rollout/vllm_rollout.py:339** - here, we need to take care of the random state. otherwise, we cannot reproduce the result.
- [ ] **luffy/verl/verl/workers/sharding_manager/base.py:7** - (sgm): add more methods if needed
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp.py:28** - (sgm): support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp.py:106** - support DCP and save sharded checkpoints
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:130** - shall we build a micro_dp group for vllm when integrating with vLLM?
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:76** - after binding to the memory buffer, we can load the checkpoint here
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:253** - (sgm): this may not be true for FSDP -> vLLM
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:273** - (zhangchi.usc1992): currently, the implementation is adhoc. We can move this function to the model
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:323** - (zhangchi.usc1992) We can consider copy non-tp weight to another infer buffer.

## 🤝 Contributing

1. Pick a TODO item from the list above
2. Create a feature branch from `dev`
3. Implement the feature
4. Submit a pull request back to `dev`

## 📄 License

TBD
