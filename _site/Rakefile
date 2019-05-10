desc "Compile and view site locally."
task :view do
  if Dir.exist?('_site')
    puts "\n## Remove _site."
    status = system("rm -r _site")
    puts status ? "Success" : "Failed"
  end
  puts "\n## Run: bundle exec jekyll serve --incremental"
  status = system("start http://localhost:4000/")
  puts status ? "Success" : "Failed"
end

desc "Compile _site"
task :compile do
  if Dir.exist?('_site')
    puts "\n## Remove _site."
    status = system("rm -r _site")
    puts status ? "Success" : "Failed"
  end
  puts "\n## Recompile _site."
  status = system("bundle exec jekyll build")
  puts status ? "Success" : "Failed"
  puts "\n## Staging modified files"
end

desc "Commit source"
task :commit do
  puts "\n## Switiching to source branch."
  status = system("git checkout source")
  puts status ? "Success" : "Failed"
  status = system("git add -A")
  puts status ? "Success" : "Failed"
  puts "Please input the commit message."
  message = $stdin.gets.chomp
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
  status = system("git push -f --all origin")
  puts status ? "Success" : "Failed"
  puts "\n## Switching back to source branch"
  status = system("git checkout source")
  puts status ? "Success" : "Failed"
end

desc "Commit and deploy _site/"
task :compile_commit_deploy => [:compile, :commit, :deploy] do
end


task :default => ["help_message"]

task :help_message do
  puts "\nTo view the website, type 'rake view'."
  puts "\nTo add current branch, type 'git add -A'."
  puts "\nTo commit current branch, type 'git push -m \"message\"'."
  puts "\nTo push current branch, type 'git push'."
  puts "\nTo compile and commit to source branch, and deploy the whole site to master branch, first type 'rake compile_commit_deploy', then type in the commit message blindly."
  end
