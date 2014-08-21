# RubyMotion Bug With 
> :headers_dir symlink patch forked from :head

## Steps
~~~ bash

# set up my custom version of rubymotion (freshly forked from hipbyte, added patch)
$ git clone jonmorehouse/rubymotion
$ rake install # set up rubymotion project etc

$ git clone jonmorehouse/rubymotion-aws
$ bundle; rake pod:install; rake build

~~~
Note that the above system works for most other pods...

## Above Steps Create the following error output

~~~ bash

rake aborted!
Command failed with status (127): [RUBYOPT='' '/Library/RubyMotion/bin/gen_br...]
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/file_utils.rb:54:in `block in create_shell_runner'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/file_utils.rb:45:in `call'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/file_utils.rb:45:in `sh'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/file_utils_ext.rb:37:in `sh'
/Library/RubyMotion/lib/motion/project/xcode_config.rb:400:in `gen_bridge_metadata'
/Library/RubyMotion/lib/motion/project/vendor.rb:226:in `block in build_xcode'
/Library/RubyMotion/lib/motion/project/vendor.rb:152:in `chdir'
/Library/RubyMotion/lib/motion/project/vendor.rb:152:in `build_xcode'
/Library/RubyMotion/lib/motion/project/vendor.rb:44:in `build'
/Library/RubyMotion/lib/motion/project/builder.rb:67:in `block in build'
/Library/RubyMotion/lib/motion/project/builder.rb:66:in `each'
/Library/RubyMotion/lib/motion/project/builder.rb:66:in `build'
/Library/RubyMotion/lib/motion/project/app.rb:78:in `build'
/usr/local/lib/ruby/gems/2.1.0/gems/motion-cocoapods-1.5.0/lib/motion/project/cocoapods.rb:53:in `build_with_cocoapods'
/Library/RubyMotion/lib/motion/project/template/ios.rb:68:in `block (2 levels) in <top (required)>'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/task.rb:240:in `call'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/task.rb:240:in `block in execute'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/task.rb:235:in `each'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/task.rb:235:in `execute'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/task.rb:179:in `block in invoke_with_call_chain'
/usr/local/Cellar/ruby/2.1.2_2/lib/ruby/2.1.0/monitor.rb:211:in `mon_synchronize'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/task.rb:172:in `invoke_with_call_chain'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/task.rb:201:in `block in invoke_prerequisites'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/task.rb:199:in `each'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/task.rb:199:in `invoke_prerequisites'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/task.rb:178:in `block in invoke_with_call_chain'
/usr/local/Cellar/ruby/2.1.2_2/lib/ruby/2.1.0/monitor.rb:211:in `mon_synchronize'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/task.rb:172:in `invoke_with_call_chain'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/task.rb:165:in `invoke'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/application.rb:150:in `invoke_task'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/application.rb:106:in `block (2 levels) in top_level'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/application.rb:106:in `each'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/application.rb:106:in `block in top_level'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/application.rb:115:in `run_with_threads'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/application.rb:100:in `top_level'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/application.rb:78:in `block in run'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/application.rb:176:in `standard_exception_handling'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/lib/rake/application.rb:75:in `run'
/usr/local/lib/ruby/gems/2.1.0/gems/rake-10.3.2/bin/rake:33:in `<top (required)>'
/usr/local/bin/rake:23:in `load'
/usr/local/bin/rake:23:in `<main>'
Tasks: TOP => build => build:simulator

~~~
