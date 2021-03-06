heredoc [source](https://www.rubyguides.com/2018/11/ruby-heredoc/)
```ruby
    it "adds links to files" do
      text = "PDF files: [links]"
      output_html = html_output_for(text, files: files)
      expected_output = <<~EXPECTED_OUTPUT.chomp
      <p>PDF files: <ul>
          <li><a href=\"https://abc.com/file.pdf\">converter</a></li>
          <li><a href=\"https://abc.com/file.pdf\">scrap_metal</a></li>
      </ul>
      </p>
      EXPECTED_OUTPUT
      expect(output_html).to eq(expected_output)
    end
```


#### Ruby's `$LOAD_PATH` - [source](https://stackoverflow.com/a/6671633/847670)
```ruby
# file_caller.rb
class FileCaller
  def call
    puts "hej. I am File"
  end
end

# main.rb
require "file_caller"
FileCaller.new.call
```

```
❯ ruby main.rb
Traceback (most recent call last):
	2: from main.rb:1:in `<main>'
	1: from ..kernel_require.rb:92:in `require'
...kernel_require.rb:92:in `require': cannot load such file -- file_caller (LoadError)
```

```
❯ ruby -I "."  main.rb
hej. I am File
```

#### Memory benchmark
```ruby
gem 'get_process_mem'

@memory_benchmarks = []
def log_memory(text)
  mem = GetProcessMem.new.mb
  @memory_benchmarks.push(mem)
  puts ("after #{text} PMEM: #{mem}")
end
```

