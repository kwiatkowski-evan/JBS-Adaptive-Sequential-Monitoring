# Software for paper "A Structured Framework for Adaptively Incorporating External Evidence in Sequentially Monitored Clinical Trials"
# By Evan Kwiatkowski, Eugenio Andraca-Carrera, Mat Soukup, Matthew A. Psioda

===========================================================================================================================================
Folder: onearm
	Description: Contains all programs and scripts necessary to perform the analyses from Section 3.1 "Single-Arm Trial with Binary Endpoint"
	The following inputs are required:
		
		[1] double  - p.skpt  -> estimate for null response probability
		[2] double  - p.enth  -> estimate for plausible, clinically meaningful risk difference
		[3] double  - sig.fut -> residual level of uncertainty used for futility monitoring
		[4] double  - sig.eff -> residual level of uncertainty used for efficacy monitoring
		[5] integer - max.ss  -> maximum sample size
		[6] integer - reps    -> integer number of simulation studies to perform;

	SUBFOLDER: CODE
	Contains R programs for design simulations.
	
		RUN ORDER:
		[1] args_model.R.     --> Parameters regarding formulation of priors
		[2] args_simulation.R --> Parameters regarding design scenarios
		[3] code_source.R.    --> Perform design simulations
	
===========================================================================================================================================\
Folder: riskdiff
	Description: Contains all programs and scripts necessary to perform the analyses from Section 3.2 "Parallel Two-Group Design with Binary Endpoint"
	The following inputs are required:
		
		[1]  double  - delta.skpt   -> estimate for null risk difference
		[2]  double  - delta.enth   -> estimate for plausible, clinically meaningful risk difference
		[3]  double  - mu     	    -> estimate for nuisance parameter
		[4]  double  - sig.fut      -> residual level of uncertainty used for futility monitoring
		[5]  double  - sig.eff	    -> residual level of uncertainty used for efficacy monitoring
		[6]  double  - freq.mntr    -> frequency of data monitoring
		[7]  integer - eff.mix.prob -> weight assigned to skeptical prior in determination for treatment efficacy
		[8]  integer - max.ss       -> maximum sample size
		[9]  integer - min.ss       -> minimum sample size
		[10] integer - reps         -> integer number of simulation studies to perform

	SUBFOLDER: CODE
	Contains R programs for design simulations.
	
		RUN ORDER:
		[1] 01_args_model.R	 --> Parameters regarding formulation of priors
		[2] 02_args_simulation.R --> Parameters regarding design scenarios
		[3] 07_code_main.R	 --> Perform design simulations

			SOURCES THE FOLLOWING:
			(a)	03_code_integrate.R  --> Perform 2-dimensional numerical integration using PRACMA package
			(b)	04_code_enrollment.R --> Sets enrollment pattern
			(c)	05_code_posteriors.R --> Parameterizes posterior distributions
			(d)	06_code_functions.R  --> Functions for determination of efficacy or futility