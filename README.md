# Modelling the US fentanyl epidemic: a tool for policy intervention

## Abstract
With a great acceleration of deaths by fentanyl overdose during the CoVid-19 pandemic, the United States are battling against synthetic opioids being smuggled inside the country and its dramatic consequences. By trying to understand the dynamics driving the fentanyl epidemic in the United States using a compartmental model, precious insights could be provided to policymakers to counter the social and economic effects illicit drugs have on the country as a whole.

Ofﬁcial data show that fentanyl-related overdose deaths have spiked after 2012. According to our model, the main parameters impacting this concerning increase are the extremely high prescription opioids addiction rates, the loose recovery rate and, of course, the deadliness of fentanyl (being 50 times more potent than heroin). Tailor-made policies should account for the sensitivity of the fentanyl epidemic system to these factors, trying not to focus on a prohibitionist approach. In fact, drug seizures and bans should be applied with care: a restrictive policy might even increase the number of fentanyl deaths by overdose in the long run.

## 1. Introduction
Fentanyl, an illicit synthetic opioid, is becoming a public health threat in the US. According to the 2020 National Drug Threat Assessment, the use of cheap and highly potent fentanyl has increased throughout the period 2019-2020 [4]. Provisional data released by the CDC in 2020 also suggest an acceleration of deaths by fentanyl overdose during the CoVid-19 pandemic [30], with 10 western states reporting over a 98 percent increase in synthetic opioid-involved deaths.

Since October 2017, the US Department of Health and Human Services has declared the opioid crisis a public health emergency [13].

To stop the alarming surge in deaths, the US government has adopted a number of intervention policies starting from the early 2000s. Solutions such as the Merida Initiative [41], the increase of boarder patrol agents [19] and the coordinated effort of DEA and the Chinese government [11] have moderately curbed the fentanyl epidemic, without having a substantial impact at the global level.

In this paper we try to model the fentanyl epidemic by making use of a compartmental model. Our aim is to understand the main drivers behind the current trend displayed by the US fentanyl epidemic in order to be able to propose more effective policy interventions. With the conviction that a simple yet precise epidemic model could help us gain relevant insights, this work is meant to shift the focus towards powerful solutions the US government can adopt in the time to come.

The ﬁrst section of this paper aims at providing a general background with regards to the fentanyl phenomenon that has been affecting the United States in the past decades. Insightful compartmental models of drug epidemics are also mentioned, together with analyses of fentanyl chemical structure and more recent ofﬁcial reports describing the American opioid epidemic. Lastly, we present the general methods used to complete our computational analysis.

In the Model section, our carefully-designed SHFR model is outlined and justiﬁed through an accurate description of the processes governing the movement of individuals within a simple compartmental system.

The third and fourth section are meant to provide the reader with a descriptive analysis of the data used to carry out the simulation and the simulation itself, respectively. By conducting an assessment of the parameters sensitivity, meaningful insights can be gained and intervention policies can be formulated in a more efﬁcient way.

Finally, the Discussion section contains possible avenues for future work, based on the analysis performed in this paper. This last section is also the bridge linking the intuitions obtained through modelling this complex system and policy interventions that governments should adopt.

## 2. Background
### (a) Fentanyl
Proposed as an alternative to morphine, which was ﬁrst isolated in its pure form between 1803 and 1817 [24], fentanyl has been used as an intravenous analgesic since late 1970s. Starting from the 1990s, fentanyl and fentanyl analogs have been found in heroin batches in the United States [20], and from 2005 the US have seen an alarming surge in fentanyl-related deaths traced to fentanyl-laced heroin sold to unsuspecting heroin users [12]. Dramatic increases in fentanyl encounters were seen again in both 2014 and 2015 [28, 26], with surges in overdose deaths due to illicitly produced fentanyl [32] imported mainly from Mexico and China [4].

Fentanyl, like similar drugs, produces µ-opioid central nervous system actions such as fatigue, sedation, nausea, vomiting, dizziness, respiratory depression, bradycardia and unconsciousness in higher doses irrespective of the mode of administration [17]. Being 75 to 100 times more potent than morphine and about 50 times stronger than heroin [39], plasma concentrations above 3 ng/mL can be fatal in most cases [27].

Difﬁculties encountered when trying to detect the presence of fentanyl and fentanyl analogs contribute to the high morbidity and mortality they are characterized by. When fentanyl overdose is detected, naloxone (a µ-opioid receptor antagonist) is administered to reverse central and peripheral effects caused by excessive intakes of opioids [38].

### (b) Litterature review
Different papers have been written about compartmental models of generic drug epidemics [10, 37, 44] and heroin diffusion processes [34]. Despite being an useful point to start from, these studies focus on processes that cannot be applied to the novel fentanyl epidemic in the United States. Fentanyl’s addictive power and deadliness make it impossible to compare it to other illicit drugs such as marijuana, heroin, cocaine and methamphetamines. Moreover, fentanyl’s dependence does not result from a gradual transition from prescription opioids or prescription fentanyl speciﬁcally [32]. For this reason, models such as the one proposed by Battista et al. [9] can still be considered relevant as they faithfully represent opioid addiction in the US from a mathematical perspective, but are not enough to account for the peculiarity of the fentanyl’s phenomenon. Despite illicit fentanyl epidemics have not been analyzed under a computational perspective so far, fentanyl case has not gone unnoticed. Its history [38] and its chemical properties [8], together with major trends in fentanyl abuse [33, 35, 14, 21, 36, 22] demonstrate that this worrying topic has been widely discussed from many different perspectives.

### (c) Methods
To better understand the drivers behind the fentanyl epidemic in the US and try to provide meaningful policy insights, simple analysis methods have been used.

Both simulation and calibration have been carried out using Python (a renowned programming language) and its integrate module (belonging to SciPy) over the governmental data gathered as explained in Section 4. On the other hand, results and sensitivity analysis have been performed with the help of Uncertainpy, a Python toolbox using Sobol sensitivity indices for uncertainty quantiﬁcation [42].

## Model
To study the evolution of the fentanyl epidemic in the United States and be able to understand the drivers behind the trend in fentanyl deaths, we consider a dynamic compartmental model. Starting from Kermack and McKendrick’s idea of SIR compartmental model [23], according to which epidemics might be modelled by dividing the population into different compartments and letting individuals pass between them according to speciﬁc parameters, we decided to approach the fentanyl epidemic under a similar computational perspective. We start by dividing the population into four different compartments, namely Susceptible, Heroin users, Fentanyl users and Recovered and model the transition between compartments according to speciﬁc parameters, as shown in Figure 1.
![](images/figure_1.png)
