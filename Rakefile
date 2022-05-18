require 'bundler/gem_tasks'  # provides several additional tasks such as build, install, and release
require 'rake/testtask'
require 'find'


desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end


# if you run one task very often, you can set it to the default task
desc 'Run tests'
task :default => :test


# block tells rake/testtask that your tests and source code reside in the
# test and lib directories, and that all your test files reside in the test
# directory, and have a name that ends with _test.rb. When you run bundle
# exec rake test now, rake/testtask will load and run all the *_test.rb files
# it can find in the test directory or any of its subdirectories. Now you
# just have to add new test files whenever you need them.
Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'Display inventory of all files'
task :inventory do
  Find.find('.') do |name|
    next if name.include?('/.') # Excludes files and directories with . names i.e. hidden files
    puts name if File.file?(name)
  end
end