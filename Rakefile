require 'html/proofer'

task :test do
  sh "jekyll build"
  HTML::Proofer.new("./_site").run
end
