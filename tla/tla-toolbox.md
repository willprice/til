# Vim mode in TLA+ Toolbox

* Run `tla-toolbox -console -consoleLog` in a terminal and press enter once the program has started. You should be met by an `osgi>` prompt.
* Type `ss p2.console`, this should print a message like:
  ```
  "Framework is launched."


  id      State       Bundle
  155     STARTING    org.eclipse.equinox.p2.console_1.1.300.v20191014-1219
  ```
* Type `start <id>` where `<id>` is the number printed in the above message, for me that was `start 155`
* Type `provaddrepo http://vrapper.sourceforge.net/update-site/stable` to add the [Vrapper](https://vrapper.sourceforge.net/home/) repo.
* Type `provlg http://vrapper.sourceforge.net/update-site/stable` to list the available installation units
* Type `provinstall net.sourceforge.vrapper.feature.group 0.74.0 DefaultProfile` to install Vrapper. This should pop up a dialog that will prompt whether you wish to continue installation or not
* Restart the IDE, you should find the editor now has vim mode support.

Information source: https://groups.google.com/g/tlaplus/c/ZY2to27DhHU
