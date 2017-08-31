### Introduction to the Bash Shell

-----

If you visit the [IP address](assignip.md) associated with your instance, your web browser will report an error, as we have yet to install and setup web server software on the machine.

We'll need to access the machine to do so, and that requires a trip to your computer's terminal and an understanding of how we can interact with machines with text.

> On Macs or Linux machines, open `Terminal` from the Applications Folder. The directions will assume macOS from here on.

> On Windows, install [Cygwin](https://www.cygwin.com) and the [ssh daemon](http://www.howtogeek.com/howto/41560/how-to-get-ssh-command-line-access-to-windows-7-using-cygwin/)

The Terminal is a way of controlling your computer without any graphical user elements. You type in commands, and the machine responds with text back to you.

macOS uses a Terminal dialect called [Bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) which is derived from its Unix ancestry. The Bash language that we will be writing is [very concise](http://ss64.com/bash/).

After Terminal launches, it will present you with a prompt.

```
ComputerName:~ user$ 
```

After the `$` you can type in commands and then hit `enter`, for instance.

`echo hello`

Your computer will return

`hello`

The `echo` command is followed by a space and an `argument`. Spaces are semantic in Bash, and separate arguments from their inputs. Any argument that `echo` takes, it spits back out. Wrapping longer arguments in quotation marks ensures that the echo command speaks back all of its input.

 `echo "hello goodbye"`
 
 `hello goodbye`
 
-----
 
Enter another Bash command 

`pwd` 

which returns something like

`/Users/zach`

`pwd` stands for 'print working directory,' and returns where your Bash shell is currently located in your computer's filesystem. Your Bash shell opens into your user home directory, which is often represented in Bash by the `~` (tilda) character. This is why your prompt includes the tilda character, it is showing you where you are currently located.

`ComputerName:~ user$ `

-----

We can see what is in the current working directory with `ls`.

`ls`

```
Applications
Desktop
Documents
Downloads
Library
Movies
Music
Pictures
```

-----

We can also maneuver around the file system `cd`, abbreviated from 'change directory.'

`cd Applications`

Typing the first few letters of where you want to go is usually enough, as the `tab` key will autocomplete. Note that Bash is *case-sensitive*.

`cd De` will autocomplete to `cd Desktop/` if you hit `tab`. You need to include the lowercase 'e' to disambiguate, as just capital letter 'D' would match `Desktop`, `Documents`, and `Downloads`.

Your prompt will update.

`ComputerName:Desktop user$` 

And then you can see the contents of your [presumably messy] Desktop with `ls`.

```
Untitled1.ai
Untitled1_Final.ai
Untitled1_Final_FINAL.ai
Untitled1_REALLY_FINAL.ai
Untitled3.ai
```

-----

We can make a folder in the working directory with `mkdir`.

`mkdir testing`

We can see the results with

`ls`

```
testing
Untitled1.ai
Untitled1_Final.ai
Untitled1_Final_FINAL.ai
Untitled1_REALLY_FINAL.ai
Untitled3.ai
```

-----

Change your working directory into this newly created folder

`cd testing/`

We can make a file in the working directory with `touch`.

`touch text.txt`

`ls` should return

`text.txt`

And we can remove files with `rm`.

`rm text.txt`

Use `ls` to ensure it is removed. Note that files are *removed immediately*, no 'empty trash' required!

-----

Create a file with `touch` and make a new directory with `mkdir`.

`touch contents.txt`

`mkdir container`

Let's check what our working directory looks like.

`ls`

```
container
contents.txt
```

Use `mv` to move a file or directory. `mv` takes two arguments: a source object to move, and a path for its new position. Note the trailing forward slash indicating that we want the file to be placed *inside* of the target directory.

`mv contents.txt container/`

`ls`

`container`

You can pass `ls` a path to see the contents of the path.

`ls container/`

`contents.txt`

`contents.txt` has been moved inside of the container directory. `mv` can also be used to rename files.

`mv container/contents.txt container/example.txt`

Check the results.

`ls container/`

`example.txt`

To delete a directory, regular `rm` is not enough -- Bash doesn't want anyone to delete a folder and inadvertantly delete its contents by accident. Most commands in Bash have several different options available for use. You can use options by placing the option indicator after the command and a hyphen. The `-r` option, short for 'recursive,' deletes a directory and its contents.

`rm -r container`

You can read about available options and command syntax by consulting the manuals for commands.

`man rm`

Checkout  manuals for the other commands introduced so far with `man`. Press the 'q' key to exit a manual.

-----

Use the `>` character to redirect output. 

`echo 'hello zach' > greetings.txt`

Unlike what you would expect, `echo` does not parrot back what you typed in this instance. Instead, the text is pushed into the `greetings.txt` file. You can read the file with the `cat` command.

`cat greetings.txt`

`hello zach`

Note that we didn't need to `touch greetings.txt`. The redirect character `>` checks if a file exists, creates it if it doesn't, and then *replaces* its contents with whatever preceded it. 

`echo 'buongiorno zacceo' > greetings.txt`

`cat greetings.txt`

`buongiorno zacceo`

If we want to add text to a file rather than replace its content, we can use `>>`.

`echo 'kalimera zahari' >> greetings.txt`

`echo 'merhaba zakhari' >> greetings.txt`

`echo 'kwey maxok' >> greetings.txt`

`echo 'rimaykullayki saksayro' >> greetings.txt`

`echo 'ohayo gozaimasu zakkun' >> greetings.txt`

Read the file to see the additions.

`cat greetings.txt`
```
buongiorno zacceo
kalimera zahari
merhaba zakhari
kwey maxok
rimaykullayki saksayro
ohayo gozaimasu zakkun
```

-----

You can `cd ..` to move up in the directory structure to exit the `testing` folder and go back to the desktop.

Use `pwd` to see that we are still in our `testing folder`

`pwd`

`/Users/zach/Desktop/testing`

Then `cd` back up to the desktop.

`cd ..`

`pwd`

`/Users/zach/Desktop/`

You can also use the `~` character to represent the home folder at any moment.

`cd ~`

`pwd`

`/Users/zach/`

-----

We can now hop back into [preparing the identity file](identityfile.md) for accessing the AWS server.
