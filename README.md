Getting Set Up
==============

### Install iTerm2 ##
You'll want to install the [latest iTerm2](http://www.iterm2.com) on your system.

After installation, if you have a problem opening "New Window" or "Preferences", then delete ~/Library/Preferences/com.googlecode.iterm2.plist and restart iTerm2

This can be done on the command line using

    rm ~/Library/Preferences/com.googlecode.iterm2.plist

### Install Android Studio ##
Install the [latest Android Studio](http://developer.android.com/sdk/installing/studio.html) on your system.

>*Known issue:* Depending on your security settings, when you attempt to open Android Studio, you might see a warning that says the package is damaged and should be moved to the trash _OR_ "Android Studio" can't be opened because it is from an unidentified developer.

>If this happens, go to Mac **System Preferences > Security & Privacy > General** and under **Allow applications downloaded from:**, select **Anywhere**. Then open Android Studio again.


### Install Android SDK ##
You'll want to install the [latest Android SDK](https://developer.android.com/sdk/index.html) on your system.

 * Download Android SDK

 * Copy 'sdk' subfolder of the Android SDK you downloaded to /Users/&lt;username>/Android/sdk

 * Set environment variable ANDROID_HOME to ~/Android/sdk

        export ANDROID_HOME=~/Android/sdk


### Install Homebrew ##
Install the [latest Homebrew](http://brew.sh/) on your system.

    ruby -e "$(curl –fsSL https://raw.github.com/mxcl/homebrew/go/install)"
    
### Install Ruby ##
Install [latest ruby 2.0.0](https://www.ruby-lang.org/en/downloads/) using RVM (“Ruby Version Manager”). 

    \curl -L https://get.rvm.io | bash -s stable --ruby


### Calabash Android ##
We use [Calabash Android](https://github.com/calabash/calabash-android/blob/master/documentation/installation.md). You'll need to follow their [installation instructions](https://github.com/calabash/calabash-android/blob/master/documentation/installation.md) to get things working on your system.

Unless you set the environment variable ANDROID_HOME, the `calabash_android` command will fail with a runtime error.
Make sure you set ANDROID_HOME environment variable in the **Install Android SDK** section above.

### Install RSpec ##
Install [RSpec](http://rspec.info/)

    gem install rspec
    
### GitHub ##
Clone project from [GitHub](https://github.com/uTest/MobileAutomation)

### Running calabash-android ##
Launch calabash-android console

    calabash-android console <my.apk>

Launch calabash-android on device:

    calabash-android run <my.apk>
    
>*Known issue:* If you get the following error:
“No keystores found. Please create one or run calabash-android setup to configure calabash-android to use an existing keystore.”
>
>debug.keystore is missing, it can be recreated in ANDROID_HOME with the following command
>
>       keytool -genkey -v -keystore ~/.android/debug.keystore -alias androiddebugkey -storepass android -keypass \
>       android -keyalg RSA -keysize 2048 -validity 10000 -dname "CN=Android Debug,O=Android,C=US"

## Installing Mobile Automation Framework (MAF) ##

### Clone the MAF Project ##
Clone the MAF project using the following command

    git clone MAF
  
### Install MAF ##
Install the MAF using the following commands

    cd <MAF project directory>
    bundle install
    rake db:create
    rake db:migrate
 
### Run MAF ##
Run the MAF application

    rails s

  


