# new-termproject

//소속 : 스포츠과학과
//이름 : 이채은 
//학번 : 20101865
//프로젝트명 : 분식천국 메뉴판
//작품 소개 : 분식집 '분식천국'을 오픈하여 손님들이 간편하게 메뉴를 주문할 수 있게 하는 프로그램을 만든다. 



// 메뉴판 이름, 메뉴 소개 시 번호 작성
def showmenu():   
    print()
    print("분식천국 메뉴판")
    for i in range(0, len(menu)):
        print(i+1, ".", menu[i], "(", price[i],"원", ")")
    print()
 
 // 메뉴 번호를 선택하여 구입할때 잔액 확인
def buy(num):    
    if money < price[num]:
        print("잔액이 부족합니다. 잔액 : %d" %money) 
        return money
    else:
        print(menu[num], " 구입완료")
        balance = money - price[num]
        print("잔액 : ", balance)
        return balance
 
 
 // 분식천국 메뉴, 가격 고지
if __name__ == '__main__':
 
    menu = ("떡볶이", "순대", "모둠튀김", "어묵탕", "피카츄돈까스", "쥬시쿨")
    price = (3000, 3000, 2000, 2000, 700, 1500)
    money = 0
    money = int( input("현금을 넣어주세요 : ") )
 
 // 메뉴 고를 때 번호를 입력하여 고를 수 있게 함
    while True:
        showmenu()
        sel = int(input("메뉴 번호를 선택하세요 (종료 : 0) : "))
        if sel == 0:
           break;
        elif(sel>=1 and sel <= len(menu)):
           money = buy(sel-1)
        else:
           print("잘못된 메뉴 번호입니다")
 
 //메뉴판을 종료하고 잔액을 반환받을 수 있게 함
    print("메뉴판 종료, 잔액 %d 반환"%money)
