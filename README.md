# `self` Discussion Questions

## Instructions

Take 30 minutes and answer the following questions together with your group. Take turns playing around with the code provided in Pry or IRB.

1 .   

      class FunnyBots  

        attr_accessor :name, :quotes  

        @@bots = []

        def initialize(name, quotes)
          @name = name
          @quotes = quotes
          @@bots << self
        end

       def random_quote
          self.quotes.sample
        end

        def self.bots
          @@bots
        end

    end

      archer = FunnyBots.new("Archer", ["Danger Zone!", "Read a book", "The cumulative hangover would literally kill me"] )

  A. What is **self** in this line ```@@bots << self``` ?  
      self == FunnyBots.new(name,quote) the instance made after initializing

  B. What is **self** in this line ```self.quotes.sample```?  
      bot1 = FunnyBots.new(whatever)
      bot1.random_quote
      self ==  bot1

  C. What kind of **method** is this & what is **self**? ```  def self.bots  
      @@bots end ```  
      class method, self == class FunnyBots

  D. Will this work ```archer.bots```? If not, why? 
      no because self refers to the class of FunnyBots which isn't the same as archer
  

2 .

    class Bicycle

      attr_reader :tire

      @@bikes = []
      @@styles = []

        def initialize(tire, gears, style)
          @tire = tire
          @gears = gears
          @style = style
          @@bikes << self
          @@styles << style
        end

        def tire_size
          @tire_size
        end

        def tire_size=(size)
          @tire_size = size
        end

        def gears
          @gears
        end

        def self.bikes
          @@bikes
        end

        def self.styles
          @@styles
        end

    end

    mongoose = Bicycle.new(4, 10, "BMX")

  For what reasons will the following method calls fail :```mongoose.tire_size = 5```, ```mongoose.gears```, ```Bicycle.bikes```, ```Bicycle.styles```? Restructure the class to fix the issues.
    ---
    mongoose.tire_size needs a setter method
    mongoose.gears fails because it's a class method not an instance method
    Bicycle.bikes doesn't exist
    Bicycle.styles doesn't exist
    ---
<p class='util--hide'>View <a href='https://learn.co/lessons/week-1-day-5-discussion'>Week 1 Day 5 Discussion</a> on Learn.co and start learning to code for free.</p>

