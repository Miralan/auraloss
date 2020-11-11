# auraloss
A collection of audio focused loss functions in PyTorch.

## Setup

```
pip install git+https://github.com/csteinmetz1/auraloss
```

## Usage

```python
import torch
import auraloss

mrstft = auraloss.freq.MultiResolutionSTFTLoss()

input = torch.rand(8,1,44100)
target = torch.rand(8,1,44100)

loss = mrstft(input, target)

```

# Loss functions

We categorize the loss functions as either time-domain or frequency-domain approaches. 

<table>
    <tr>
        <th>Loss function</th>
        <th>Interface</th>
        <th>Reference</th>
    </tr>
    <tr>
        <td colspan="3" align="center"><b>Time domain</b></td>
    </tr>
    <tr>
        <td>Error-to-signal ratio (ESR)</td>
        <td><code>auraloss.time.ESRLoss()</code></td>
        <td><a href=https://arxiv.org/abs/1911.08922>Wright & Välimäki, 2019</a></td>
    </tr>
    <tr>
        <td>DC error (DC)</td>
        <td><code>auraloss.time.DCLoss()</code></td>
        <td><a href=https://arxiv.org/abs/1911.08922>Wright & Välimäki, 2019</a></td>
    </tr>
    <tr>
        <td>Log hyperbolic cosine (Log-cosh)</td>
        <td><code>auraloss.time.Logcosh()</code></td>
        <td><a href=https://openreview.net/forum?id=rkglvsC9Ym>Chen et al., 2019</a></td>
    </tr>
    <tr>
        <td>Signal-to-distortion ratio (SDR)</td>
        <td><code>auraloss.time.SDRLoss()</code></td>
        <td><a href=https://ieeexplore.ieee.org/document/1643671>Vincent et al., 2006</a></td>
    </tr>
    <tr>
        <td>Scale-invariant signal-to-distortion ratio (SI-SDR)</td>
        <td><code>auraloss.time.SISDRLoss()</code></td>
        <td><a href=https://arxiv.org/abs/1811.02508>Le Roux et al., 2018</a></td>
    </tr>
    <tr>
        <td colspan="3" align="center"><b>Frequency domain</b></td>
    </tr>
    <tr>
        <td>Spectral convergence</td>
        <td><code>auraloss.freq.SpectralConvergenceLoss()</code></td>
        <td><a href=https://arxiv.org/abs/1808.06719>Arik et al., 2018</a></td>
    </tr>
    <tr>
        <td>Log STFT magnitude </td>
        <td><code>auraloss.freq.LogSTFTMagnitudeLoss()</code></td>
        <td><a href=https://arxiv.org/abs/1808.06719>Arik et al., 2018</a></td>
    </tr>
    <tr>
        <td>Aggregate STFT</td>
        <td><code>auraloss.freq.STFTLoss()</code></td>
        <td><a href=https://arxiv.org/abs/1808.06719>Arik et al., 2018</a></td>
    </tr>
    <tr>
        <td>Multi-resolution STFT</td>
        <td><code>auraloss.freq.MultiResolutionSTFTLoss()</code></td>
        <td><a href=https://arxiv.org/abs/1910.11480>Yamamoto et al., 2019</a></td>
    </tr>
    <tr>
        <td>Random-resolution STFT</td>
        <td><code>auraloss.freq.RandomResolutionSTFTLoss()</code></td>
        <td><a href=></a>Steinmetz & Reiss, 2020</td>
    </tr>
    <tr>
        <td>Sum and difference STFT loss</td>
        <td><code>auraloss.freq.SumAndDifferenceSTFTLoss()</code></td>
        <td><a href=https://arxiv.org/abs/2010.10291>Steinmetz et al., 2020</a></td>
    </tr>
    <tr>
        <td colspan="3" align="center"><b>Perceptual transforms</b></td>
    </tr>
    <tr>
        <td>Sum and difference signal trasform</td>
        <td><code>auraloss.perceptual.SumAndDifference()</code></td>
        <td><a href=#></a></td>
    <tr>
    <tr>
        <td>FIR pre-emphasis filters</td>
        <td><code>auraloss.perceptual.FIRFilter()</code></td>
        <td><a href=https://arxiv.org/abs/1911.08922>Wright & Välimäki, 2019</a></td>
    </tr>
</table>

# Cite
If you use this code in your work please consider citing us.
```
@inproceedings{steinmetz2020auraloss,
    title={auraloss: {A}udio focused loss functions in {PyTorch}},
    author={Steinmetz, Christian J. and Reiss, Joshua D.},
    booktitle={Digital Music Research Network One-day Workshop (DMRN+15)},
    year={2020}}
```
