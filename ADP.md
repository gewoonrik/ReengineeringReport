We have searched for cyclic dependencies between packages using the Analyze Cyclic Dependencies feature in IntelliJ.
A lot of interfaces in the package eu.sqooss.service extend AlitheiaCoreService in the package eu.sqooss.core. These interfaces are also referenced in the eu.sqooss.core.AlitheaCore class.
This means that the package eu.sqooss.service depends on the package eu.sqooss.core (via the AlitheiaCoreService interface), but the eu.sqooss.core package also depends on the eu.sqooss.service package (via the AlitheaCore class), so this is an ADP violation.
Besides that, a lot of classes in the package eu.squooss.impl.service implement interfaces from the eu.sqooss.service package. These are then bounded to these interfaces in the eu.sqooss.core.AlitheaCore class, so this is also an ADP violation.