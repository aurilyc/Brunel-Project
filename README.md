# Brunel-Project

RNA structure in health and disease - investigation of snoRNA cluster in the imprinted Dlk1-Dio3 region

Russell Hamilton & Anne Ferguson-Smith
Department of Genetics, University of Cambridge, Downing Street, Cambridge, CB2 3EH

The epigenetic phenomenon of genomic imprinting leads to specific genes being expressed in a parent-specific manner. Imprinted genes have key roles in placenta and embryo development, as well as an emerging role in brain development and function. The Dlk1-Dio3 imprinted region contains two maternally expressed small nucleolar RNA (snoRNA) clusters, SNORD113 & SNORD114, containing 9 and 31 copies respectively (10.1016/j.tig.2008.03.011). Human patients with disruptions in this conserved region display growth retardation and facial dysmorphism (10.1038/ng.2007.56). However little is known about the mechanism of action of the snoRNAs in this region. Deletion of the related SNORD116 cluster (paternally expressed) in the SNRPN imprinted region has been shown to be a direct cause of Prader-Willi syndrome and postnatal growth retardation (10.1038/ng.158; 10.1371/journal.pgen.0030235). 

Using open source computational tools we will model the snoRNA 2D and 3D structures of the Dlk1-Dio3 region (10.7490/f1000research.1117078.1). Transcribed as a precursor long non-coding RNA, Rian/MEG8, the C/D box motif containing snoRNAs have been shown to be directed by genomic imprinting and, unusually for snoRNAs, to have brain specific expression. snoRNA have previously been shown to contain Ca2+ sensitive kink-turn (KT) motifs. In low Ca2+, the KTs are in an extended confirmation, but with increased Ca2+ develop a pronounced 60o kink, opening up the nucleotide bases for sequence specific recognition. KT motifs can therefore act as a Ca2+ sensitive switch for mediating protein or tertiary RNA interactions. The brain specific expression of these C/D snoRNAs and demonstration of the existence of calcium sensitive KT motifs would provide valuable insight into these enigmatic snoRNAs and their role in the nervous system. 

Infernal search

SNO.aurilyconstantino@ctr-web:~/Cambridge project/infernal-1.1.3$ mv SNO.sto.txt SNO.sto
aurilyconstantino@ctr-web:~/Cambridge project/infernal-1.1.3$ cmbuild SNO.cm SNO.sto
# cmbuild :: covariance model construction from multiple sequence alignments
# INFERNAL 1.1.1 (July 2014)
# Copyright (C) 2014 Howard Hughes Medical Institute.
# Freely distributed under the GNU General Public License (GPLv3).
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# CM file:                                            SNO.cm
# alignment file:                                     SNO.sto
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
#                                                                      rel entropy
#                                                                      -----------
# idx    name                     nseq eff_nseq   alen  clen  bps bifs    CM   HMM description
# ------ -------------------- -------- -------- ------ ----- ---- ---- ----- ----- -----------
       1 SNORD113                   59     9.32    109    75    5    0 0.753 0.716 Small nucleolar RNA SNORD113/SNORD114 family
#
# CPU time: 0.30u 0.00s 00:00:00.30 Elapsed: 00:00:00.31
aurilyconstantino@ctr-web:~/Cambridge project/infernal-1.1.3$ cmcalibrate SNO.cm
# cmcalibrate :: fit exponential tails for CM E-values
# INFERNAL 1.1.1 (July 2014)
# Copyright (C) 2014 Howard Hughes Medical Institute.
# Freely distributed under the GNU General Public License (GPLv3).
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# CM file:                                     SNO.cm
# number of worker threads:                    12
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
#
# Calibrating CM(s):
#
#                        predicted                                                   actual
#                       running time              percent complete                running time
# model name            (hr:min:sec)  [........25........50........75..........]  (hr:min:sec)
# --------------------  ------------  ------------------------------------------  ------------
  SNORD113                  00:03:59  [==Error: Unable to establish connection with R session
============
======
====================]      00:04:19
#
# Calibration summary statistics:
#
#                           exponential tail fit mu        exponential tail fit lambda         total number of hits
#                       -------------------------------  -------------------------------  -------------------------------
# model name            glc cyk glc ins loc cyk loc ins  glc cyk glc ins loc cyk loc ins  glc cyk glc ins loc cyk loc ins
# --------------------  ------- ------- ------- -------  ------- ------- ------- -------  ------- ------- ------- -------
  SNORD113                -3.79   -0.70    3.21    4.78    0.368   0.400   0.646   0.609    94621   72278  382510  251093
#
# CPU time: 2956.77u 6.25s 00:49:23.02 Elapsed: 00:04:19.63
[ok]

aurilyconstantino@ctr-web:~/Cambridge project/infernal-1.1.3$ mv Dlk1.rtf Dlk1.fa
aurilyconstantino@ctr-web:~/Cambridge project/infernal-1.1.3$ cmsearch SNO.cm Dlk1.fa
# cmsearch :: search CM(s) against a sequence database
# INFERNAL 1.1.1 (July 2014)
# Copyright (C) 2014 Howard Hughes Medical Institute.
# Freely distributed under the GNU General Public License (GPLv3).
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# query CM file:                         SNO.cm
# target sequence database:              Dlk1.fa
# number of worker threads:              12
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -


aurilyconstantino@ctr-web:~/Cambridge project/infernal-1.1.3$ cmsearch SNO.cm Dlk1.fa

# cmsearch :: search CM(s) against a sequence database
# INFERNAL 1.1.1 (July 2014)
# Copyright (C) 2014 Howard Hughes Medical Institute.
# Freely distributed under the GNU General Public License (GPLv3).
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# query CM file:                         SNO.cm
# target sequence database:              Dlk1.fa
# number of worker threads:              12
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

Query:       SNORD113  [CLEN=75]
Accession:   RF00181
Description: Small nucleolar RNA SNORD113/SNORD114 family
Hit scores:
 rank     E-value  score  bias  sequence  start    end   mdl trunc   gc  description
 ----   --------- ------ -----  -------- ------ ------   --- ----- ----  -----------

   [No hits detected that satisfy reporting thresholds]


Hit alignments:

   [No hits detected that satisfy reporting thresholds]


Internal CM pipeline statistics summary:
----------------------------------------
Query model(s):                                                  1  (75 consensus positions)
Target sequences:                                                1  (22666 residues searched)
Target sequences re-searched for truncated hits:                 1  (712 residues re-searched)
Windows   passing  local HMM SSV           filter:              43  (0.3975); expected (0.35)
Windows   passing  local HMM Viterbi       filter:                  (off)
Windows   passing  local HMM Viterbi  bias filter:                  (off)
Windows   passing  local HMM Forward       filter:               4  (0.04603); expected (0.02)
Windows   passing  local HMM Forward  bias filter:               3  (0.0308); expected (0.02)
Windows   passing glocal HMM Forward       filter:               0  (0); expected (0.02)
Windows   passing glocal HMM Forward  bias filter:               0  (0); expected (0.02)
Envelopes passing glocal HMM envelope defn filter:               0  (0); expected (0.02)
Envelopes passing  local CM  CYK           filter:               0  (0); expected (0.0001)
Total CM hits reported:                                          0  (0); includes 0 truncated hit(s)

# CPU time: 0.02u 0.02s 00:00:00.04 Elapsed: 00:00:00.03
//
[ok]

##Please note: although the covariation model and its subsequent calibration ran smoothly, the cmsearch using Dlk1 and the .sto file of the SNORD113/114 family did not find similarities between the codes. Have to check Dlk1 file and run search again. 

References

Barlow, D.P., Stoger, R., Herrmann, B.G., Saito, K. and Schweifer, N. (1991) 'The mouse insulin-like growth factor type-2 receptor is imprinted and closely linked to the Tme locus', Nature, 349(6304), pp. 84-87. doi: 10.1038/349084a0 [doi].

Dawson, W.K. and Bujnicki, J.M. (2016) 'Computational modeling of RNA 3D structures and interactions', Current opinion in structural biology, 37, pp. 22-28. doi: 10.1016/j.sbi.2015.11.007 [doi].

Edwards, C.A., Mungall, A.J., Matthews, L., Ryder, E., Gray, D.J., Pask, A.J., Shaw, G., Graves, J.A., Rogers, J., SAVOIR consortium, Dunham, I., Renfree, M.B. and Ferguson-Smith, A.C. (2008) 'The evolution of the DLK1-DIO3 imprinted domain in mammals', PLoS biology, 6(6), pp. e135. doi: 10.1371/journal.pbio.0060135 [doi].

Enterina, J.R., Enfield, K.S.S., Anderson, C., Marshall, E.A., Ng, K.W. and Lam, W.L. (2017) 'DLK1-DIO3 imprinted locus deregulation in development, respiratory disease, and cancer', Expert review of respiratory medicine, 11(9), pp. 749-761. doi: 10.1080/17476348.2017.1355241 [doi].

Li, E., Beard, C. and Jaenisch, R. (1993) 'Role for DNA methylation in genomic imprinting', Nature, 366(6453), pp. 362-365. doi: 10.1038/366362a0 [doi].

Magnus, M., Boniecki, M.J., Dawson, W. and Bujnicki, J.M. (2016) 'SimRNAweb: a web server for RNA 3D structure modeling with optional restraints', Nucleic acids research, 44(W1), pp. 315. doi: 10.1093/nar/gkw279 [doi].

Samarsky, D.A., Fournier, M.J., Singer, R.H. and Bertrand, E. (1998) 'The snoRNA box C/D motif directs nucleolar targeting and also couples snoRNA synthesis and localization', The EMBO journal, 17(13), pp. 3747-3757. doi: 10.1093/emboj/17.13.3747 [doi].

Schmidt, J.V., Matteson, P.G., Jones, B.K., Guan, X.J. and Tilghman, S.M. (2000) 'The Dlk1 and Gtl2 genes are linked and reciprocally imprinted', Genes & development, 14(16), pp. 1997-2002.

Wang, J., Mao, K., Zhao, Y., Zeng, C., Xiang, J., Zhang, Y. and Xiao, Y. (2017) 'Optimization of RNA 3D structure prediction using evolutionary restraints of nucleotide-nucleotide interactions from direct coupling analysis', Nucleic acids research, 45(11), pp. 6299-6309. doi: 10.1093/nar/gkx386 [doi].
