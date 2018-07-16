require 'elo'

class Elo < Thor
  desc 'calculate', 'calculate new elo score'
  def calculate
    team1 = ::Elo::Player.new(rating: ask('Team 1 ELO before match: ').to_i)
    team2 = ::Elo::Player.new(rating: ask('Team 2 ELO before match: ').to_i)

    winner = ask('Which team won, 1 or 2: ')

    if winner == '1'
      team1.wins_from(team2)
    elsif winner == '2'
      team2.wins_from(team1)
    else
      abort('Bad input, try again')
    end

    puts "Team 1: #{team1.rating}"
    puts "Team 2: #{team2.rating}"
  end
end
