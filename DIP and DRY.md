The interface eu.sqooss.service.fds.InMemoryCheckout depends on the low level eu.sqooss.service.fds.InMemoryDirectory which is a violation of the Dependency Inversion Principle.

In the class eu.sqooss.service.db.ProjectVersion a lot of duplicate is shared between the getLiveFilesCount and getVersionFiles methods. 
Furthermore, in the same class the methods getVersionByRevision and getVersionByTimestamp are exactly the same aside from one parameter.