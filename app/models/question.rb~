
class Question < ActiveRecord::Base
  attr_accessible :text
  has_many :choices
  has_many :result, :through=>:user_answers
  has_one :user_answer
  
  def answer
	 uncorrect
	 choices.select {|c| c.correct}[0]
  end	
  
  def uncorrect
	 choices.each {|c| c.correct = false}
  end
  
  def answer= choice
	 if !answer.nil?
		answer.correct = false
	 end
	 
	 if choices.include? choice
		choice.correct = true
	 else
		choices << choice
		choice.correct = true
	 end
  end
  def to_s
    text
  end
end
