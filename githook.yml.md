# .githook.yml
GitHooks.io looks for a YAML file called `.githook.yml` in the root of your repository. It should look something like this:

```yaml
title:       Hello World
description: "Description of my Hello World application." # optional. Defaults to the description on GitHub.
thumbnail:   http://path/to/thumbnail.jpg                 # optional. Defaults to your user avatar.

# relative to the root
entry_point: hello-world.js

# specify the AWS Lambda wrapper to run your GitHook inside (defaults to `node`)
wrapper: node

# require at least one event to trigger the GitHook. See 'Events' below.
triggered_on:
  - push

# optional. Add as many scopes as required. See 'Scopes' below.
# Note that 'admin:repo_hook' will always be available (since it is required by GitHooks.io to properly manage GitHook installations) - but you should still specify it if you need it, just to be safe.
scopes_required:
  - 'user:email'

# optional - see "Parameterised GitHooks" below
parameters:
  'my_parameter_name':
    title:       Name
    description: Who am I greeting?
    # options: 'string', 'url', 'number', 'boolean', 'select'. default: 'string'
    type:        string
    # options: 'true', 'false'. default: 'false'
    required:    false
  'curry_flavour':
    title:       Curry flavour
    description: What are you eating?
    options: # only valid for `select` type. First provided option will be the default
      - Beef
      - Chicken
      - Vegetable

```
