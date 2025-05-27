# $\partial$-CROWN: Verification for Physics-Informed Neural Networks

Code associated with the paper "Efficient Error Certification for Physics-Informed Neural Networks" published at [ICML 2024](https://icml.cc/Conferences/2024).

If you use it in your work, please cite the following:
```
@inproceedings{
  eiras2024efficient,
  title={Efficient Error Certification for Physics-Informed Neural Networks},
  author={Francisco Eiras and Adel Bibi and Rudy R Bunel and Krishnamurthy Dj Dvijotham and Philip Torr and M. Pawan Kumar},
  booktitle={Forty-first International Conference on Machine Learning},
  year={2024},
  url={https://openreview.net/forum?id=5t4V7Q6lmz}
}
```

This work was supported by the EPSRC Centre for Doctoral Training in Autonomous Intelligent Machines and Systems [EP/S024050/1], by Five AI Limited, by the UKRI grant: Turing AI Fellowship EP/W002981/1, and by the Royal Academy of Engineering under the Research Chair and Senior Research Fellowships scheme.


Installation Instructions:
1. Clone this repository and go into the directory: 

```
git clone https://github.com/JosephZouRHIT/partial_crown_plus.git
cd partial_crown_plus                                                     
```

2. Clone oval-bab from their Github repository:

```
git clone https://github.com/oval-group/oval-bab.git 
```

3. Add the following function to oval-bab/tools/bab_tools/onnx_reader.py after import if rebuild_tanh does not exist in this file:

def rebuild_tanh(node, weights):
    return nn.Tanh(), node.input, node.output

4. Create conda virtual environment with Python version <= 3.12 (For compatibility with PyDOE, which may be removed later).

```
conda create -y -n partial-crown python=3.11
conda activate partial-crown
```

5. From the project root directory, install required Python packages: 

```
python -m pip install -r requiremnts.txt
```

6. Install both partial_crown and oval-bab to make sure the namespaces are correct:

```
cd oval-bab
python -m pip install .
cd ..
python -m pip install .
```
