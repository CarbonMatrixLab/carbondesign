## CarbonDesign
Protein sequence design is critically important for protein engineering. Despite recent advancements in deep learning-based methods, achieving accurate and robust sequence design remains an ongoing challenge. Here, we present CarbonDesign, a new approach that draws inspiration from successful ingredients of AlphaFold and makes significant developments tailored specifically for sequence design. At its core, CarbonDesign explores Inverseformer to learn representations from backbone structures and an amortized Markov Random Fields model for sequence decoding. Moreover, we incorporate other essential AlphaFold concepts into CarbonDesign: an end-to-end network recycling technique to leverage evolutionary constraints from protein language models and a multi-task learning technique for generating side chain structures alongside designed sequences. CarbonDesign outperforms other methods on independent test sets including CASP15, CAMEO, and de novo proteins from RFDiffusion. Furthermore, it supports zero-shot prediction of the functional effects of sequence variants, making it a promising tool for applications in bioengineering.

**Installation**\
Please install the required libraries using install.sh.

**Usage**\
You are required to input the **PDB** file (**--data_dir**) of the protein backbone structures. CarbonDesign will subsequently output the designed protein sequence (**--output_dir**). Additionally, CarbonDesign supports the prediction of the side chain structures of the designed sequences (**--save_sidechain**).
````python
python -u run_carbondesign.py 
--model ../data/models/default_model.ckpt ## model name
--model_features ./config/config_data_mrf2.json ## feature config
--model_config ./config/config_model_mrf_pair_enable_esm_sc.json ## model config
--data_dir ../data/pdbs ## input pdbs path
--output_dir ../ results ## results path
--device gpu ## use GPU
--gpu_idx 0 ## gpu index
--name_idx ../data/pdbs/name.idx ## list of sequences that need to be designed is required
--temp 0.01 ##sampling temperature
````
**Citation**\
Highly accurate and robust protein sequence design with CarbonDesign.  M. Ren, C. Yu, D. Bu, H. Zhang. Nature Machine Intelligence, In press.

## CarbonMatrix Team
We aim to develop large-scale deep learning and generative AI models for protein structure prediction and protein design. We have already released CarbonDesign, and we plan to release more models in the near future.

Current members:\
Haicang Zhang, team leader\
Milong Ren, Tian Zhu, Zaikai He, Siyuan Tao
