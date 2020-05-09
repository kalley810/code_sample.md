# code_sample.md
This is the code portion of the project
import random
def printoptions():
    print("what would you like to do? \n")
    print("1. play again")
    print("2. view statistics")
    print("3. quit\n")
    option = int(input("enter choice: "))
    return option

def loadgame():
    username = input("enter your name: ")
    try:
        fin = open(username+".rps","r")
        result = {"name": "", "wins": 0, "loss": 0, "tie": 0}
        i = 0
        for line in fin:
            if i is 0:
                result['name'] = line.strip()
            elif i is 1:
                    result['wins'] = int(line)
            elif i is 2:
                        result['loss'] = int(line)
            elif i is 3:
                            result['tie'] = int(line)
                            i = i + 1
                            return result
    except:
                            print("hello "+username+" your game file does not found")
                            result = loadgame()
                            return result
def quitgame(result):
                            fout = open(result["name"]+".rps","w")
                            fout.write(result['name']+"\n"+str(result['wins'])+"\n"
                                       +str(result['loss'])+"\n"+str(result['tie']))
                            fout.close()
                            print(result['name']+", your game has been saved.")

                            def printstatistics(total,resuklt):
                                print(result['name']+", here are your game play statistics...")
                                print("wins: "+str(result['wins']))
                                print("losses: "+str(result['loss']))
                                print("ties: "+str(result['tie']))
                                if result['loss'] is 0:
                                    print ("\nwin/loss ratio: 0")
                                else:
                                        print("\nwin/loss ratio: "+str(round(result['wins']/result['loss'],2)))
                                        temp = printoptions()
                                if temp is 1:
                                            playgame(total + 1, result)
                                elif temp is 2:
                                                printstatistics(total,result)
                                elif temp is 3:
                                                    quitgame(result)
                                else:
                                                        print("enter a valid entry")
                                                        printstatistics(total,result)
                                                        def getvalue(x):
                                                            if x is 1:
                                                                return "rock"
                                                            elif x is 2:
                                                                return "paper"
                                                            elif x is 3:
                                                                return "scissors"
                                                            def findwinner(user,comp):
                                                                if user is 1 and comp is 2:
                                                                    return "comp"
                                                                elif user is 1 and comp is 3:
                                                                    return "user"
                                                                elif user is 2 and comp is 1:
                                                                    return "user"
                                                                elif user is 2 and comp is 3:
                                                                    return "comp"
                                                                elif user is 3 and comp is 1:
                                                                    return "comp"
                                                                elif user is 3 and comp is 2:
                                                                    return "user"
                                                                else:
                                                                    return "tie"

                                                                def playgame(total,result):
                                                                    print("round "+str(total))
                                                                    print("\n1. rock")
                                                                    print("2. paper")
                                                                    print("3. scissors\n")
                                                                    choice = int(input("what will it be? "))
                                                                    if choice <= 3 and choice >= 1:
                                                                        computervalue = random.randint(1,3)
                                                                        print(computervalue)
                                                                        winner = findwinner(choice,computervalue)
                                                                        if winner is "user":
                                                                            print("you chose "+getvalue(choice)+". the computer chose "
                                                                                  +getvalue(computervalue)+". you win!")
                                                                            result['wins'] = result['wins'] + 1
                                                                        elif winner is "comp":
                                                                                print("you chose " + getvalue(choice) + ". the computer chose " +getvalue(computervalue) + ". you lose!")
                                                                                result['lose'] = result['lose'] + 1
                                                                        elif winner is "tie":
                                                                                    print("you chose " + getvalue(choice) + ". the computer chiose " + getvalue(computervalue) + ". game tied")
                                                                                    result['tie'] = result['tie'] + 1
                                                                    else:
                                                                                        print("please enter a number that is in the range 1 to 3")
                                                                                        playgame(total,result)
                                                                                        temp = printoptions()
                                                                                        if temp is 1:
                                                                                            playgame(total+1,result)
                                                                                        elif temp is 2:
                                                                                                printstatistics(total,result)
                                                                                        elif temp is 3:
                                                                                                    quitgame(result)
                                                                                        else:
                                                                                                        print("enter a valid choice!")

                                                                                                        def startnewgame():
                                                                                                            name = input("what is your name? ")
                                                                                                            print("hello "+name+". let's play!")
                                                                                                            result = {"name":name,"wins":0,"loss":0,"tie":0}
                                                                                                            playgame(1,result)

                                                                                                            print("welcome to rock, paper, scissors")
                                                                                                            print()
                                                                                                            print("1. start new game")
                                                                                                            print("2. load game")
                                                                                                            print("3. quit")
                                                                                                            print("")
                                                                                                            option = int(input("enter choice: "))
                                                                                                            if option is 1:
                                                                                                                startnewgame()
                                                                                                            elif option is 2:
                                                                                                                    result = loadgame()
                                                                                                                    print("welcome back, "+result['name']+ " let's play again!")
                                                                                                                    total = result['wins'] + result['loss'] + result['tie']
                                                                                                                    temp = printoptions()
                                                                                                                    if temp is 1:
                                                                                                                        playgame(total + 1, result)
                                                                                                                    elif temp is 2:
                                                                                                                            printstatistics(total,result)
                                                                                                                    elif temp is 3:
                                                                                                                                quitgame(result)
                                                                                                                    else:
                                                                                                                                    print("enter a valid choice!")
                                                                                                                                    
                                                                                                                                    
                                                                                                                                    
                                                                                                                                    
                                                                                                                                    
                                                                                                                                     [Back to Home](https://github.com/kalley810/Final-Project)
