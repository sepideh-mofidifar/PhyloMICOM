<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>PhyloMICOM</title>
</head>
<body>

<h1>PhyloMICOM</h1>

<p>PhyloMICOM is an extension of the <strong>MICOM</strong> package, designed to improve the accuracy and efficiency of microbial community simulations by incorporating phylogenetic relationships. This project introduces a modified version of the <code>community.py</code> file from the MICOM package, along with additional scripts and data for analysis.</p>

<h3>Installation</h3>

<p>PhyloMICOM is available on PyPi and can be installed via:</p>

<pre><code>pip install PhyloMICOM==0.1.0</code></pre>

<h3>micom Folder</h3>

<p>This folder contains the original <strong>MICOM</strong> package, with a key modification to the <code>community.py</code> file. The modification, known as <strong>PhyloMICOM</strong>, pools the metabolic models of phylogenetically related organisms at the order level. This allows for more accurate and phylogenetically-informed simulations of microbial communities.</p>

<h4>Example usage:</h4>

<p>To use the PhyloMICOM package, you can import the following functions:</p>

<pre><code>
from micom import load_pickle
from micom.workflows import build
from micom.data import test_medium
from micom.qiime_formats import load_qiime_medium
</code></pre>

<h4>Building community models:</h4>

<p>To build a community model with PhyloMICOM, you can use the following code:</p>

<pre><code>
manifest = build(data, out_folder="models", model_db=test_db, cutoff=0.0001, threads=2)
</code></pre>

<h4>Performing a community simulation:</h4>

<p>To perform a community simulation, you can load your Qiime medium and run the model:</p>

<pre><code>
medium = load_qiime_medium('western_diet_gut.qza')
growth_results = grow(manifest, model_folder="models", medium=medium, tradeoff=0.5, threads=2)
</code></pre>

<h3>analysis Folder</h3>

<p>This folder includes a collection of Python scripts used to analyze microbial communities. These scripts are tailored to work with the PhyloMICOM framework and provide tools for various types of analyses, such as sensitivity testing, growth rate prediction, and statistical evaluations.</p>

<h3>data Folder</h3>

<p>The data folder contains all the input datasets used for running simulations and the corresponding output data generated by PhyloMICOM. This includes metagenomic data, configuration files, and simulation results. The input data is structured to be easily accessible for rerunning or extending the analyses performed in this project.</p>

<h3>License</h3>

<p>PhyloMICOM is developed for non-commercial use and is provided as-is. Contributions are welcome and appreciated. For inquiries about collaborations or commercial usage and development, please contact us at <a href="mailto:s.mofidifar@gmail.com">s.mofidifar@gmail.com</a>.</p>

</body>
</html>
