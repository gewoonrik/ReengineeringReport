The interface eu.sqooss.service.fds.InMemoryCheckout depends on the low level eu.sqooss.service.fds.InMemoryDirectory which is a violation of the Dependency Inversion Principle.

We have used the Locate Duplicates feature of IntelliJ to find duplicated code. To make sure that we find only relevant duplicated code we have set the minimum lines of duplicate code to be 15.
This feature found a lot of duplicate code so we only give some examples.
In the class eu.sqooss.service.db.ProjectVersion a lot of duplicate is shared between the getLiveFilesCount and getVersionFiles methods.
Furthermore, in the same class the methods getVersionByRevision and getVersionByTimestamp are exactly the same aside from one parameter.
These violations of the DRY principle can both be fixed by moving the duplicate code to a seperate method.
Finally, the classes WebAdminRenderer and ProjectsView contain duplicate HTML code. This could be solved by moving the HTML code to template methods which get filled based on parameters.