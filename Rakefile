posts_dir = File.join(".", "_posts")

desc "Make a new post in #{posts_dir}"
task :new_post, :title do |t, args|
  if args.title
    title = args.title
  else
    print "Title: "
    title = STDIN.gets.chomp
  end
  raise "--- No posts directory! Is Jekyll installed?" unless FileTest.directory?(posts_dir)
  filename = "#{posts_dir}/#{Time.now.strftime('%Y-%m-%d')}-#{title.gsub(/[ ]/, '-')}.md"
  puts "Creating post #{filename}"
  open(filename, 'w') do |post|
    post.puts "---"
    post.puts "layout: post"
    post.puts "title: #{title}"
    post.puts "date: #{Time.now.strftime('%Y-%m-%d %H:%M:%S %z')}"
    post.puts "categories: "
    post.puts "---"
  end
end