The SourceMod project base is a framework and template for larger SourceMod plugins. It's using a modular architecture with tools and libraries that help you focus on what the plugin itself should do.

This is not a functional SourceMod plugin.  A normal server host wouldn't have any use for this.  This was made for plugin developers of larger plugins that seek more organization and simplicity in their jumbled mass of code.

The project works like this:
You download this project and build your plugin off of it.  All you do as a coder, is make "modules" that the base loads and manages.  Modules can communicate through API provided by the base files.  Some immediate benefits of this system are: Modules can easily be disabled, events are easily handled separately in each module, translations are handled by the base and provide a multitude of API functions to easily send translated strings, client access for any parts of your module are easily handled, and your module can be exported as an independent plugin with only a few tweaks.

This base comes with 5 components.  4/5 of these components are optional, 1 is required.

- modulemanager.inc
> This is the most important file in this project.  This project will not compile without this file.  This is the only required component of the base.

- eventmanager.inc
> This is the second most important file, while the project will compile without it, it's highly recommended for easily forwarding game events, SM forwards, and even custom events to any module in your project.

- logmanager.inc
> This is an API that any modules are able to use to log messages.  It includes features such as a way to filter out logging in certain modules and allow it in others, can print log messages to admin chat or public chat.  The project will compile without this file if logging isn't needed in your plugin.

- translationsmanager.inc
> Allows modules to register with this and automatically have their own translations file loaded (translations/project/moduleshortname.phrases.txt)  The project will compile without this file if your plugin doesn't need to be multi-lingual.

-clientaccessmanager.inc
> Provides an API to check if clients have access to certain parts of your plugin.  The project will compile without this file.