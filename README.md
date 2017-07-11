# CAStlE: A Domain Specific Language for Engineering Collective Adaptive Systems

## Contributors

This study has been designed, developed, and reported by the following investigators:

* <b> Antonio Bucchiarone </b> - Fondazione Bruno Kessler (FBK), Trento - Italy

* <b> Antonio Cicchetti </b> - Malardalen University, Vasteras - Sweden

* <b> Martina De Sanctis </b> - Fondazione Bruno Kessler



## Theoretical fundation of CAStlE

CAStlE is a domain-specific language (DSL) for designing collective adaptive systems (CAS)s. In order to benefit from the adoption of separation-of-concerns principles, it is made-up of three different views that address different aspects of a CAS. In particular, a view is devoted to the definition of an adaptive system, a view deals with the specification of ensembles, and one view tackles the definition of collective adaptation. Each of the views is based on a specific sub-language, whose syntax is defined in terms of a meta-model. Whereas, the semantics of CAStlE is implicitly defined in terms of the mappings between model elements and the corresponding behaviour enacted by the DeMOCAS execution engine. Essentially, the three metamodels abstract CASs by mirroring the formalization illustrated in [1], [2]. Therefore, for further details about the formalization the reader is referred to the just mentioned paper.  

### The Adaptive System Metamodel

The <i>Adaptive System metamodel</i> is shown in the following figure.

<p align="center">
  <img src="https://github.com/das-fbk/CAS-DSL/blob/master/AdaptiveSystemMM.png" width="1000"/>
</p>

In particular an AdaptiveSystem is a composition of <i>DomainObjects</i>, each of which has a name and contains: a <i>CoreProcess</i>; <i>Fragment</i>(s); <i>DomainProperty</i>(ies). Both CoreProcess and Fragment are a composition of <i>State</i>(s), <i>Transition</i>(s), <i>Activity</i>(ies), and <i>Annotation</i>(s). They are used to define the behaviour provided by a domain object in terms of state/transition systems enriched with activities and annotations. Both processes and fragments act over <i>DomainProperty</i>(ies), that represent internal and external knowledge for a domain object. In the case of internal knowledge, the domain object contains the corresponding property, while in case of external knowledge the domain object just refers to a property by means of an association. DomainProperty(ies) are state/transition systems as well.

### The Ensemble Model Metamodel

The <i>Ensemble Model metamodel</i> is shown in the following.

<p align="center">
  <img src="https://github.com/das-fbk/CAS-DSL/blob/master/ensembleModelMM.png" width="800"/>
</p>

An <i>Ensemble</i> is a composition of <i>Role</i>(s) and <i>IssueType</i>(s). Each Role is, indeed, the role through which a certain domain object participates in an ensemble. Interconnected with its role, there are a number of <i>RoleParameter</i>(s) and <i>Preference</i>(s) defined for the domain object. A role can trigger issues defined in the ensemble and provide <i>Solver</i>(s) compatible with certain <i>IssueType</i>(s). Both issues and solvers can defined their own parameters. It is important to notice that the DomainObject concept of this metamodel is directly linked to the one in the Adaptive System metamodel through the <i>domainObjectSpecification</i> link. This entails that at modelling level it will only be possible to define roles in an ensemble model for domain objects already defined in an adaptive system model.

### The Collective Adaptation Model Metamodel

The <i>Collective Adaptation Model</i> metamodel is shown in the following figure. 

<p align="center">
  <img src="https://github.com/das-fbk/CAS-DSL/blob/master/CollectiveAdaptationMM.png" width="700"/>
</p>

A Collective Adaptation is a composition of <i>EvenHandler</i>(s), which are defined over <i>RoleActivity</i>(ies) grouped in scopes. <i>Handlers</i> catch <i>Event</i>(s), i.e. issues, and counteract with <i>Adaptation</i>(s), i.e. solvers. Also in this case, <i>RoleActivity</i>, <i>IssueType</i>, and <i>Solver</i> entities are directly connected with their definitions in Adaptative System and Ensemble, therefore it will only be possible to define collective adaptations based on elements already existing in an adaptative system and in an ensemble model, respectively.

## References

**1.** A. Bucchiarone, M. De Sanctis, A. Marconi, M. Pistore and P. Traverso, *“Incremental composition for adaptive by-design service based systems,”* in IEEE International Conference on Web Services, ICWS, 2016, pp. 236–243.

**2.** A. Bucchiarone, M. De Sanctis, and A. Marconi, *“Decentralized dynamic adaptation for service-based collective adaptive systems,”*
in Workshop on Adaptive Service-oriented and Cloud Applications (ASOCA at ICSOC), 2016.
