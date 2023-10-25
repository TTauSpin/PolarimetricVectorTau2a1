# PolarimetricVectorTau2a1
Numeric computation of polarimetric vector for tau->a1->pi- pi0 pi0 nu and tau->a1->pi- pi+ pi- nu decays

# Setup

```bash
git clone https://github.com/TTauSpin/PolarimetricVectorTau2a1 $CMSSW_BASE/src/TauAnalysis/PolarimetricVectorTau2a1
git remote set-url origin git+ssh://git@github.com/TTauSpin/PolarimetricVectorTau2a1
```

# How to use the code

```bash
  // reco::Candidate::LorentzVector p1     is the four-vector of the first  same-sign pion [1,2]
  // reco::Candidate::LorentzVector p2     is the four-vector of the second same-sign pion [1,2]
  // reco::Candidate::LorentzVector p3     is the four-vector of the opposite-sign pion    [3]
  // integer                        charge is the sum of the three pions charge
  // reco::Candidate::Vector        h      is the polarimeter vector
  //
  //  [1] the two pi- in tau- -> pi- pi+ pi- nu decays
  //          two pi+ in tau+ -> pi+ pi- pi+ nu decays
  //          two neutral pions in tau+/- -> pi+/- pi0 pi0 nu decays
  //  [2] the ordering of the two same-sign pions does not matter
  //  [3] the pi+ in tau- -> pi- pi+ pi- nu decays
  //          pi- in tau+ -> pi+ pi- pi+ nu decays
  //          charged pion in tau+/- -> pi+/- pi0 pi0 nu decays
  //
  // Note that p1, p2, p3 need to be given in the tau-lepton restframe
  //
  PolarimetricVectorTau2a1 a1pol;
  reco::Candidate::Vector h = a1pol(p1, p2, p3, charge, PolarimetricVectorTau2a1::k3ChargedPi);
```
