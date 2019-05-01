desc "Compile and view site locally."
task :view do
  puts "\n## Run: bundle exec jekyll serve --incremental"
  status = system("start http://localhost:4000/")
  puts status ? "Success" : "Failed"
end

desc "Commit source"
task :commit do
  puts "\n## Switiching to source branch."
  status = system("git checkout source")
  puts status ? "Success" : "Failed"
  puts "\n## Staging modified files"
  status = system("git add -A")
  puts status ? "Success" : "Failed"
  puts "\n## Committing a source at #{Time.now.utc}"
  message = "Built from source at #{Time.now.utc}"
  status = system("git commit -m \"#{message}\"")
  puts status ? "Success" : "Failed"
  puts "\n## Pushing commits to remote"
  status = system("git push origin source")
  puts status ? "Success" : "Failed"
end

desc "Deploy _site/ to master branch"
task :deploy do
  puts "\n## Deleting master branch"
  status = system("git branch -D master")
  puts status ? "Success" : "Failed"
  puts "\n## Creating new master branch and switching to it"
  status = system("git checkout -b master")
  puts status ? "Success" : "Failed"
  puts "\n## Forcing the _site subdirectory to be project root"
  status = system("git filter-branch --subdirectory-filter _site/ -f")
  puts status ? "Success" : "Failed"
  puts "\n## Pushing all branches to origin"
  status = system("git push -f origin")
  puts status ? "Success" : "Failed"
  puts "\n## Switching back to source branch"
  status = system("git checkout source")
  puts status ? "Success" : "Failed"
end

desc "Commit and deploy _site/"
task :commit_deploy => [:commit, :deploy] do
end

task default: %w[commit_deploy]
