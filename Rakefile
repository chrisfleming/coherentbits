require 'nanoc/tasks'



desc 'Setup twitter bootstrap'
task :bootstrap do
  # Build css
  puts "***** RUNNING SHELL CMD *****"
  system "cd ./vendor/bootstrap/less; lessc ./bootstrap.less > ../../../content/assets/css/bootstrap.css" 

end


desc 'Create new article'
task :blog, [:slug] do |t, args|
  now = Time.new

  dir = "./content/#{now.strftime("%Y/%m/%d")}/"
  FileUtils.mkdir_p dir

  outfile  =File.new("#{dir}/#{args.slug}.html","w")
  if outfile
    outfile.syswrite("---\n")
    outfile.syswrite("title:\n")
    outfile.syswrite("kind: article\n")
    outfile.syswrite("author: Chris Fleming\n")
    outfile.syswrite("created_at: #{now.strftime("%Y-%M-%D")}\n" )
    outfile.syswrite("updated_at: #{now.strftime("%Y-%m-%d")}\n" )
    outfile.syswrite("---")
  end

end

