# PolarimetricVectorTau2a1
Numeric computation of polarimetric vector for tau->a1->pi- pi0 pi0 nu and tau->a1->pi- pi+ pi- nu decays

# Setup

```bash
git clone https://github.com/TTauSpin/PolarimetricVectorTau2a1 $CMSSW_BASE/src/TauAnalysis/PolarimetricVectorTau2a1
git remote set-url origin git+ssh://git@github.com/TTauSpin/PolarimetricVectorTau2a1
```

The code depends on the ROOT and ROOT math libraries. It is left to the user to install and link those libraries.

# How to use the code

```bash
  // PolarimetricVectorTau2a1::LorentzVector p1      is the four-vector of the first  same-sign pion                        [1,2]
  // PolarimetricVectorTau2a1::LorentzVector p2      is the four-vector of the second same-sign pion                        [1,2]
  // PolarimetricVectorTau2a1::LorentzVector p3      is the four-vector of the opposite-sign pion                            [3]
  // integer                                 charge  is the charge-sum of the three pion system                              [4]
  // PolarimetricVectorTau2a1::DecayChannel  channel flag indicating whether tau decays into pi- pi+ pi- or into pi- pi0 pi0 [5]
  // PolarimetricVectorTau2a1::Vector        h       is the polarimetric vector
  //
  //  [1] the two pi- in tau- -> pi- pi+ pi- nu decays
  //          two pi+ in tau+ -> pi+ pi- pi+ nu decays
  //          two neutral pions in tau+/- -> pi+/- pi0 pi0 nu decays
  //  [2] the ordering of the two same-sign pions does not matter
  //  [3] the pi+ in tau- -> pi- pi+ pi- nu decays
  //          pi- in tau+ -> pi+ pi- pi+ nu decays
  //          charged pion in tau+/- -> pi+/- pi0 pi0 nu decays
  //  [4] use -1 for tau-
  //          +1 for tau+
  //  [5] use PolarimetricVectorTau2a1::k3ChargedPi for tau- -> pi- pi+ pi- nu and tau+ -> pi+ pi- pi+ nu decays
  //          PolarimetricVectorTau2a1::kChargedPi2NeutralPi for tau+/- -> pi+/- pi0 pi0 nu decays
  //
  // Note that p1, p2, p3 need to be given in the tau-lepton restframe.
  // The tasks of reconstructing the tau-lepton restframe and performing the Lorentz-boosts 
  // of p1, p2, and p3 from the laboratory frame to the tau-lepton restframe is left to the user code.
  //
  PolarimetricVectorTau2a1 a1pol;
  PolarimetricVectorTau2a1::Vector h = a1pol(p1, p2, p3, charge, channel);
```
