rSpec
======


pending -> can be used in the middle of the prase: it 'should ... ' pending end

```
module Codebreaker
  class Game
    def initialize(output)
      @output = output
    end
    def start
      @output.puts 'Welcome to Codebreaker!'
    end
  end
end
```
```
module Codebreaker
  describe Game do
    describe "#start" do
      it "sends a welcome message" do
        output = double('output')
        game = Game.new(output)
        output.should_receive(:puts).with('Welcome to Codebreaker!')
        game.start
      end
      it "prompts for the first guess" do
        output = double('output')
        game = Game.new(output)
        output.should_receive(:puts).with('Enter guess:')
        game.start
      end
    end
  end
end

```
