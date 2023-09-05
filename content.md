# Ruby Gym: Sum Odd Integers

Write a program that receives any amount of numbers separated by spaces. The program should then print the sum of the odd numbers.  

For example, if the input was `["9", "5", "4"]`, the program should only sum the "9" and the "5", because those are odd numbers, and print

```
"14"
```

Get the expected output for the randomly `sample`d `numbers` below, and then get the tests to pass.

```ruby
inputs = [
  ["9", "5", "4"],
  ["20", "40", "60"],
  ["1", "3", "19"]
]
numbers = inputs.sample
pp numbers
# write your program below
```
{: .repl #sum_odd_integers title="Sum Odd Integers" readonly_lines="[1,2,3,4,5,6,7,8]"}


```ruby
describe "Sum Odd Integers" do
  it "prints '14' when the numbers are ['9', '5', '4']" do
    path = "/tmp/code.rb"

    allow_any_instance_of(Array).to receive(:sample).and_return(["9", "5", "4"])

    File.foreach(path) do |line|
      if line.match(/^p.*14/)
        expect(line).to_not match(/14/),
          "Expected graded code block to NOT print the Integer literal '14', but did."
      end
    end

    output = capture_stdout { require_relative(path) }
    expect(output).to match(/14/), "Expected output to be '14', but was '#{output}'."
  end

  def capture_stdout
    old_stdout = $stdout
    $stdout = StringIO.new
    yield
    $stdout.string
  ensure
    $stdout = old_stdout
  end
end
```
{: .repl-test #sum_odd_integers_test_1 for="sum_odd_integers" title="Sum Odd Integers prints '14' when the numbers are ['9', '5', '4']" points="1"}


```ruby
describe "Sum Odd Integers" do
  it "prints '0' when the numbers are ['2', '4', '6']" do
    path = "/tmp/code.rb"

    allow_any_instance_of(Array).to receive(:sample).and_return(["2", "4", "6"])

    File.foreach(path) do |line|
      if line.match(/^p.*0/)
        expect(line).to_not match(/0/),
          "Expected graded code block to NOT print the Integer literal '0', but did."
      end
    end

    output = capture_stdout { require_relative(path) }
    expect(output).to match(/0/), "Expected output to be '0', but was '#{output}'."
  end

  def capture_stdout
    old_stdout = $stdout
    $stdout = StringIO.new
    yield
    $stdout.string
  ensure
    $stdout = old_stdout
  end
end
```
{: .repl-test #sum_odd_integers_test_2 for="sum_odd_integers" title="Sum Odd Integers prints '0' when the numbers are ['2', '4', '6']" points="1"}


```ruby
describe "Sum Odd Integers" do
  it "prints '5' when the numbers are ['1', '1', '3']" do
    path = "/tmp/code.rb"

    allow_any_instance_of(Array).to receive(:sample).and_return(["1", "1", "3"])

    File.foreach(path) do |line|
      if line.match(/^p.*5/)
        expect(line).to_not match(/5/),
          "Expected graded code block to NOT print the Integer literal '5', but did."
      end
    end

    output = capture_stdout { require_relative(path) }
    expect(output).to match(/5/), "Expected output to be '5', but was '#{output}'."
  end

  def capture_stdout
    old_stdout = $stdout
    $stdout = StringIO.new
    yield
    $stdout.string
  ensure
    $stdout = old_stdout
  end
end
```
{: .repl-test #sum_odd_integers_test_3 for="sum_odd_integers" title="Sum Odd Integers prints '5' when the numbers are ['1', '1', '3']" points="1"}
