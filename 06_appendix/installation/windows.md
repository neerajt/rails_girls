# Windows Install Guide

Install Ruby and Rails via RailsFTW:

[http://railsftw.bryanbibat.net/](http://railsftw.bryanbibat.net/)

Select the big red button that says "Download Latest", and when the download is finished, run the `rails-ftw-[some_numbers].exe` file.

The default install options are good, you should not need to change anything. The only thing to watch out for is that the "Install Location" part does not contain any spaces. Ninety-nine percent of the time, it should not have any by default.

### Git via msysgit

Next, we need the 'msysgit' package from a Google Code repository:

[http://msysgit.github.io/](http://msysgit.github.io/)

Download the most recent version (first in the list). As of October 2014, it will be named `Git-1.9.4-preview[some_numbers].exe`. When it is done downloading, run the file and install with the default options.

When it is done installing, open your start menu (or start screen in Windows 8) and type "bash" in the text box. An option called "Git Bash" should come up. Run that program.

This is your terminal. You will be using this to enter all sorts of commands tomorrow. To make sure everything worked properly, type:

```bash
ruby -v
```

And hit enter. The next line should show something that starts with "ruby 2.1", possibly with more numbers afterward, a date, and the word "mingw32". Those are all completely fine.

Next run the command, being careful to use the exact spaces and hyphens:

```bash
gem install bundler --no-ri --no-rdoc
```

And it should say "Successfully installed bundler-1.5.3" and another line "1 gem installed". If that has worked out, you're all set!

## ImageMagick for Image Uploads on Windows

In order to use various image-related tools for one of our Explorations tomorrow, you will need to install three extra tools: The Ruby DevKit, ImageMagick and a gem called rmagick.

### Ruby DevKit

First head over to [http://rubyinstaller.org/downloads/](http://rubyinstaller.org/downloads/)

and in the left-hand column, under the **Devlopment Kit** section, select the download for "Ruby 2.0 and 2.1" for 32-bit. They should be named "DevKit-mingw32-[lots of numbers]-sfx.exe". Run that and extract it to a location *with no spaces in the name* (here we will use C:\Ruby\DevKit). Then in your "Git Bash" window (or open a new one), you will want to run

```bash
$ cd C:\Ruby\DevKit
$ ruby dk.rb init
$ ruby dk.rb install -f
```

Open File Explorer and go to `C:\Ruby\DevKit` and double click the `devkitvars.bat` file. This will open a file quickly and then close it. Close all window and Ruby Bash.


### ImageMagick

Go to [http://ftp.sunet.se/pub/multimedia/graphics/ImageMagick/binaries/ImageMagick-6.7.7-10-Q8-windows-dll.exe](http://ftp.sunet.se/pub/multimedia/graphics/ImageMagick/binaries/ImageMagick-6.7.7-10-Q8-windows-dll.exe)

This will download a file on your computer. Open your download folder, right click the file, and Run as Administrator.

**This next part is important.** When you get to the Select Desination Location within the install wizard change the path to `C:\ImageMagick`. Hit 'Next' until you get to the Select Additional Tools screen. Unclick the "Create Desktop Icon" and click the "Install development headers and libraries for C and C++. Then move on to Install.

Open Command by going to Start Menu (or start screen in Windows 8) type cmd into the search, right click Command Prompt and Run as Administrator. When the command prompt opens run

```bash
gem install rmagick -- '--with-opt-dir="C:/ImageMagick"'
```
