## Project Overview
This project demonstrates a specialized **Fintech AI Agent** powered by a fine-tuned **Meta Llama 3.1 8B** model. The agent is capable of understanding banking contexts, conducting natural conversation, and securely executing specific tools (checking balances, listing transactions, and blocking cards) when necessary.

## Key Features
*   **Intent Recognition**: Distinguishes between general chat and actionable banking requests.
*   **Tool Injection**: Trained to output structured `<tool_code>` tags for backend execution.
*   **Efficient Fine-Tuning**: Uses **QLoRA** (4-bit quantization) and LoRA adapters for memory-efficient training on consumer GPUs (Colab).
*   **Mock Backend**: A simulated banking database environment to validate tool execution logic.

## Technical Stack
*   **Base Model**: `meta-llama/Meta-Llama-3.1-8B-Instruct`
*   **Libraries**: `transformers`, `peft`, `bitsandbytes`, `trl`, `wandb`
*   **Dataset**: Custom filtered subset of Bitext Customer Support dataset + Synthetic Tool Injection.

## Supported Tools
The model is trained to invoke the following Python functions:
1.  `get_balance(user_id)`: Retrieves current account funds.
2.  `get_transactions(user_id, count)`: Lists recent spending history.
3.  `block_card(user_id, card_id, reason)`: Emergency action for lost/stolen cards.
