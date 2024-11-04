# 50B-token runs

This folder contains two runs generated by extending the 11/03/24 speedrun record to 50B FineWeb tokens.

They compare different optimizers for the transformer body. The head and embedding are always optimized by Adam.

* [Muon](./4fbe61ec-f79a-4c19-836d-46d599deecce.txt) The final model gets 36.17 on HellaSwag.
* [Adam](./3d715d41-453a-40d6-9506-421ba69766b2.txt) The final model gets 34.05 on HellaSwag.

Some HellaSwag baselines:
* Karpathy's baseline llm.c training (trained for 10B FineWeb tokens): 29.9
* OpenAI GPT-2 (124M): 29.4
* OpenAI GPT-3 (124M) (trained for 300B WebText tokens): 33.7
* Huggingface SmolLM2-135M (trained for 2T FineWeb/DCLM/etc tokens): 42.1

Note: I'm a little concerned that the learning rate schedule (WSD) and weight decay (zero), which are tuned for the speedrun duration,
might become undertuned/suboptimal for trainings of this duration.
It does look like the gap between Muon/Adam is too large to be closed by something like this, and the HellaSwag scores look quite reasonable, but you never know.
