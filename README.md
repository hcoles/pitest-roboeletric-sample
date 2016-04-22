# Deckard (for Maven)

This fork of Deckard has been minimally modified to support mutation testing.

To mutation test use the pitest profile eg.

```
mvn -Ppitest test
```

After first following the original Deckard instructions below.

Deckard is the simplest possible Android project that uses Robolectric for testing and Maven to build. It has one Activity (with an empty layout), and a Robolectric test that creates that Activity.

Deckard also imports seamlessly into IntelliJ, due to IntelliJ's support for Maven. Just import the pom.xml.

Eclipse is also supported. Install the [m2e-android](http://rgladwell.github.io/m2e-android/) plugin for Eclipse, and import the project as a Maven project.
After importing into Eclipse, you have to mark the consume-aar goal as ignored, since aar consumption is not yet supported by m2e-android.
To do this, simply apply the Quick fix on the "Plugin execution not covered by lifecycle configuration" error.

## Setup

*Note: These instructions assume you have a Java 1.6 [JDK](http://www.oracle.com/technetwork/java/javase/downloads/index.html) installed.*

To start a new Android project:

1. Install the [Android SDK](http://developer.android.com/sdk/index.html). On Mac OS X with [Homebrew](http://brew.sh/) just run:
    ```bash
    brew install android-sdk
    ```

2. Set your `ANDROID_HOME` environment variable to `/usr/local/opt/android-sdk`.

3. Install Maven if you haven't already (run `mvn` to check). On OS X (as before) this is easiest with [Homebrew](http://brew.sh/):
	```bash
	brew install maven
	```

4. Download Deckard from GitHub:
    ```bash
    wget https://github.com/robolectric/deckard-maven/archive/master.zip
    unzip master.zip
    mv deckard-maven-master my-new-project
    ```

5. Run the setup script to install dependencies into Maven:
    ```bash
    my-new-project/setup.sh
    ```

6. In the project directory you should be able to run the tests:
    ```bash
    cd my-new-project
    mvn clean test
    ```

7. Optionally, import the project into IntelliJ (or Eclipse) by selecting 'Import Project' in IntelliJ and selecting the project's `pom.xml`. When prompted to pick an SDK you just need to select the Android SDK home and your JDK.

8. Change the names of things from 'Deckard' to whatever is appropriate for your project. Package name, classes, and the AndroidManifest are good places to start.

9. Build an app. Win.
