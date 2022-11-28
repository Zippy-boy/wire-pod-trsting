Welcome to the wire-pod wiki!

***

# Wiki Links

* [Installation Guide](./Installation.md)

* [Dev Documentation](./Standards.md)

* [More general tips, guides, and info](./Things-to-Know.md)

***

# What wire-pod is

**wire-pod** is custom voice server software for the Anki (now Digital Dream Labs) Vector robot. It is an alternative to the official Escape Pod product and does not require any payment to Digital Dream Labs nor any connection to their servers. It works with every Vector 1.0, **including ones which haven't been unlocked**.

***


# Features

- Every voice command is implemented
- Weather commands (easy to setup via weatherapi.com or openweathermap.org)
- Knowledgegraph commands (easy to setup via houndify)
- Token and jdocs, so a robot can "sign in" to it
- A robot can sign in to wire-pod without ever touching a DDL server
- A robot can sign in to wire-pod without needing to clear user data
- There is a Vector app replacement hosted at port 8080 (by default) which allows you to configure bot settings and to control the robot with your keyboard
- It is easy to create your own voice commands via plugins (see [Standards.md](./Standards.md)) and to implement the vector-go-sdk into your plugins
    - Contrary to popular belief, the vector-go-sdk is fully featured and relatively easy to use

***

# Compatibility

## OS support
- Linux
    - Debian (apt)
    - Arch (pacman)
    - Fedora (dnf)
- Windows
    - Under WSL

## Architecture support
- x86_64
- aarch64
- armhf

***

# How

* It is all thanks to Digital Dream Labs for open-sourcing the [chipper voice server software](https://github.com/digital-dream-labs/chipper) and for creating Escape Pod in the first place.

* The Raspberry Pi Escape Pod images contain compiled `chipper` binaries packed with `upx`. It was easy to run `upx -d` on them and to open them up in a hex editor then to take out the pub/priv key combo. Those certificates are now located in `~repo/chipper/epod`. This is what allows compatibility with production robots running escape pod software.

* The community has also played a huge role in fleshing out wire-pod and making it what it is.

***

# Vocabulary

* **DDL** - Digital Dream Labs acronym

* **chipper** - what the voice server itself is called and may be referred to as.

* **SDK** - software development kit. This is also what allows services such as the mobile app to communicate with Vector.

* **vector-cloud** or **vic-cloud** - the program on the robot which makes the request to chipper.

* **intent** - when text is transcribed, the software will match it with a set of words to find out what "intent" best matches what was said, so the bot knows exactly what to do. For instance, "good robot" and similar phrases will end up as "intent_imperative_praise".

* **STT** - speech-to-text

* **production robots** - Vectors that were sold to consumers and were set up like normal.

* **OSKR/dev-unlocked bots** - Vectors that have been unlocked by Anki, DDL, or by a developer who paid for OSKR (open-source kit for robots).