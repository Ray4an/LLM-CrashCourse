# LLM-CrashCourse

Here's a 9-hour crash course curriculum for learning to build LLM applications.

All resources are free.

𝗣𝗔𝗥𝗧 𝟭 - 𝗔 𝗚𝗘𝗡𝗧𝗟𝗘 𝗜𝗡𝗧𝗥𝗢 𝗧𝗢 𝗟𝗟𝗠𝗦 (1h 30m)

Intro & overview of language models, next-word prediction, embeddings, cosine similarity, semantic search

Resources: <br>
📺 30m: Simple intro (MBerm) https://lnkd.in/eCfYMdUK <br>
📖 40m: llms nohype (MRied) https://lnkd.in/eY6Pd9bJ <br>
📺 10m: Next wrd prd (LBouc) https://lnkd.in/ergd9FT2 <br>
📺 10m: Sem search (LSerr) https://lnkd.in/eRnnhmuj <br>

---

𝗣𝗔𝗥𝗧 𝟮 - 𝗧𝗥𝗔𝗡𝗦𝗙𝗢𝗥𝗠𝗘𝗥 𝗔𝗥𝗖𝗛𝗜𝗧𝗘𝗖𝗧𝗨𝗥𝗘 (1h 30m)

Encoder-decoder architecture, masking, attention, transformers, GPTs

Resources: <br>
📺 30m: Visual llm (3Blu1Br) https://lnkd.in/egJPUhuX <br>
📺 20m: Enc-Dec (JStarm) https://lnkd.in/eJNfAKZ8 <br>
📺 10m: Attention (LSerr) https://lnkd.in/eEFrS5uV <br>
📺 15m: Transformers (LSerr) https://lnkd.in/eVcnZxad <br>
📺 15m: GPTs (DataBrks) https://lnkd.in/es9bKS-z <br>

---

𝗣𝗔𝗥𝗧 𝟯 - 𝗣𝗥𝗢𝗠𝗣𝗧 𝗘𝗡𝗚𝗜𝗡𝗘𝗘𝗥𝗜𝗡𝗚 (2h 0m)

Zero/one/few-shot, chain-of-thought, self-consistency, generated knowledge, prompt chaining, ReAct

Resources: <br>
📺 60m: PE Overview (ESarav) https://lnkd.in/eFF2Yc7C <br>
📖 90m: Prompt Eng (DAIR) https://lnkd.in/eaqPT63j <br>
📖 30m: PE Guide (Brex) https://lnkd.in/etPjrkvw <br>
⚒️ 0m: LangChain Hub https://lnkd.in/e_pt2cVx <br>

---

𝗣𝗔𝗥𝗧 𝟰 - 𝗖𝗛𝗔𝗜𝗡𝗜𝗡𝗚, 𝗥𝗔𝗚, 𝗩𝗘𝗖𝗧𝗢𝗥 𝗗𝗕𝗦, 𝗔𝗚𝗘𝗡𝗧𝗦 (2h 30m)

Langchain, RAG, vector databases, LlamaIndex, Open AI functions

Resources: <br>
📺 30m: LngCh ckbk1 (GKam) https://lnkd.in/eRTUH3rZ <br>
📺 30m: LngCh ckbk2 (GKam) https://lnkd.in/ehXZNsRg <br>
⚒️ 0m: LngCh tutorials (GKam) https://lnkd.in/eSyFQwhm <br>
📖 30m: Adv RAG (HugFace) https://lnkd.in/eSqe-UCD <br>
📺 5m: Vector dbs (Fireshp) https://lnkd.in/et3Zz8-k <br>
📺 10m: LC+Pinecone (GKam) https://lnkd.in/e5E6Fv46 <br>
📺 20m: LlamaIdx (engprmpt) https://lnkd.in/eYRFG-wg <br>
📺 30m: OpenAI fn/agnt (auto) https://lnkd.in/esZa7c3s <br>

---

𝗣𝗔𝗥𝗧 𝟱 - 𝗙𝗜𝗡𝗘𝗧𝗨𝗡𝗜𝗡𝗚 (1h 30m)

Feature-based finetuning, LoRA, RLHF

Resources: <br>
📖 15m: Finetuning (SRasc) https://lnkd.in/eTdFHQS5 <br>
📖 15m: FT v PrmpEng (NBant) https://lnkd.in/ekeHKWPe <br>
📺 30m: RLHF intro (HugFac) https://lnkd.in/etsH53ri <br>
📖 15m: RLHF guid (Lblerr) https://lnkd.in/e57dsuEp <br>
📖 15m: LoRA (HugFac) https://lnkd.in/ervJK9C7 <br>


---

# 10 Supervised fine-tuning (SFT) tips when starting a new LLM project. Here are our default settings for GPUs (A100 and newer):

3️⃣ Start with 3 epochs <br>
📉 LR: 2e-5 with a cosine schedule & 0.1 warmup ratio <br>
🔗 Apply Packing to combine samples up to a sequence length (2048) <br>
📏 Try Global BS of 256/512 (e.g., BS=16 per device, grad_acc=2/4 on 8xH100s) <br>
⚡ Use Flash Attention v2 with bf16 & tf32 (to speed up remaining fp32 calculations) <br>
💾 Enable gradient checkpointing to save memory <br>
🚀 Opt for “adamw_torch_fused” (10% speed up) or “adamw_torch” optimizer <br>
🖥️ Deepspeed & FSDP both work well for distributed training <br>
⚙️ Consider LoRA for quicker iterations with less compute <br>
🤗 Use the SFTTrainer from Hugging Face TRL <br>
