
task :default => :serve

desc "Serve with debug"
task :serve do
  sh('LISTEN_GEM_DEBUGGING=1 bundle exec jekyll serve --host 0.0.0.0 --port 4000')
end

desc "Build"
task :build do
  sh('bundle exec jekyll build')
end
