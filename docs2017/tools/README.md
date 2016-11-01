Welcome
=======

This is a repository containing Cloudant documentation content,
to be published on IBM Bluemix.

Issues and PRs welcome.

Cloning the submodules
----------------------

The Bluemix markdown content is built using the `marked-it*` toolkits.
They are included as git submodules for this repository.
When you clone this repository,
you'll see that the `tools/marked-it*` directories are empty.

To obtain the code,
run these commands (a once-only task):

	git submodule init
	git submodule update
	cd tools/marked-it-cli
	npm install ../marked-it
	npm install

You should now find that the `tools/marked-it*` directories are populated.
You do not need to perform this task again.

Note: If you want to get the latest versions of `marked-it*`,
simply run the `git submodule update` command again.

**Note**: The `marked-it*` modules are only available internally within IBM.
However, they are basically markdown build scripts with some additional
capabilities for Bluemix-specific 'extras'.
It is not essential to have these tools; they are only used for building
a local preview of content. It is still perfectly possible to do a 'pure'
markdown-only build of the content for local preview purposes.