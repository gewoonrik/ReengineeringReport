The abstract class \verb|Job| contains a lot of methods. Its main responsibility is to represent the concept of a `job'. To accomplish this it contains properties (e.g. state, dependencies, dependees) and methods (addDependency, removeDependency, dependsOn) to alter its state. However, the class also exposes a method called verb|execute()|. This indicates that the \verb|Job| class is also responsible for executing a job. We argue that this is a violation of the SRP, because there is more than one motive for chaning the \verb|Job| class: either if the way we represent a job changes, or if the way we execute a job changes. A better architecture would be to move the job execution out of the \verb|Job| class and into a service layer (for example, \verb|JobExecuter|).

% Refs: www.objectmentor.com/resources/articles/srp.pdf, https://twitter.com/jeffrey_way/status/527857091470700544, http://verraes.net/2014/09/objects-as-contracts-for-behaviour/, http://msdn.microsoft.com/en-gb/magazine/dn385704.aspx, https://blog.inf.ed.ac.uk/sapm/2014/02/04/the-anaemic-domain-model-is-no-anti-pattern-its-a-solid-design/

------------

The abstract class \verb|Job| contains an abstract method \verb|priority()|. Thus, every concrete Job is expected to have a property. It turns out that most of the implementing classes indeed have a priority. However, \verb|ProjectDeleteJob| has a priority set to 0xff. This indicates that `priority' is actually not a property of \verb|ProjectDeleteJob|. The value of 0xff is added to the class to satisfy the contract. The same reasoning applies to \verb|TestJob|, \verb|UpdaterJob|, \verb|OhlohUpdater|, \verb|MetricSchedulerJob|, which have fixed priority 0, 0, 3, 0x2.

------------

\verb|ClusterNodeServiceImpl.java| is responsible for doing a HTTP GET request (\verb|void doGet|), sending XML response (\verb|sendXMLResponse|), constructing XML response (\verb|createXMLResponse|), assigning a project to a cluster (assignProject). This feels like a violation of the SRP.

------------

ADP = Acyclic Dependencies Principle (source: http://butunclebob.com/ArticleS.UncleBob.PrinciplesOfOod)

------------