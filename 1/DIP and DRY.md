The interface eu.sqooss.service.fds.InMemoryCheckout depends on the low level eu.sqooss.service.fds.InMemoryDirectory which is a violation of the Dependency Inversion Principle, because high level abstractions should depend on other high level abstractions.

We have used the Locate Duplicates feature of IntelliJ to find duplicated code.
We have found a lot of duplicate code so we only give the most significant violations.
In the class eu.sqooss.service.db.ProjectVersion 10 lines of code is shared between the getLiveFilesCount and getVersionFiles methods.
Furthermore, in the same class the methods getVersionByRevision and getVersionByTimestamp are exactly the same aside from one parameter.
These violations of the DRY principle can both be fixed by moving the duplicate code to a seperate method which accepts the right parameters.
Finally, the classes WebAdminRenderer and ProjectsView contain duplicate HTML code. This could be solved by moving the HTML code to template methods which get filled based on parameters.