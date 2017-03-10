<!--- Copyright (C) 2009-2016 Lightbend Inc. <https://www.lightbend.com> -->
Play Activator templates
========================

This project contains the built-in Play Activator templates. The list of templates
and their source directories is configured in the `build.sbt` file. Each template
is generated by combining the files from several directories together and then
replacing strings in the files.

* `build.sbt` - configuration for generating the templates
* `play-common` - files shared by the Scala and Java seed templates
* `play-java` - files for the Java seed template
* `play-scala` - files for the Scala seed template
* `play-java-intro` - files for the Java introduction template
* `play-scala-intro` - files for the Scala introduction template

Developing
----------

The templates sources are partly generated, which means you need to "build" them before
you can run them.

There is a `syncTemplates` command that will build the templates and keep them in sync
with the sources as they change. The most convenient way to use this is to use triggered
execution:

    sbt ~syncTemplates

Then in another window, you can test/run the template, for example, to run the
`play-scala` template:

    ./buildTemplate play-scala run

Or you can even run activator in it:

    ./buildTemplate play-java ui

Now edit the template itself in this directory, and every time you save, the changes
will be saved, the template processend and synced to the directory where activator
is running.

Publishing
----------

You can publish templates by running

    sbt publishTemplates

You can publish specific templates by using the templates command:

    sbt templates play-scala publishTemplates