#
# ____        _____   ____  _____ ____ ____   ___ ____   ___  
#|  _ \ _   _|___ /  / ___|| ____/ ___|___ \ / _ \___ \ / _ \ 
#| |_) | | | | |_ \  \___ \|  _|| |     __) | | | |__) | | | |
#|  __/| |_| |___) |  ___) | |__| |___ / __/| |_| / __/| |_| |
#|_|    \__, |____/  |____/|_____\____|_____|\___/_____|\___/ 
#       |___/                                                 
#__        ___   _    _  _____ ____    _    ____  ____  
#\ \      / / | | |  / \|_   _/ ___|  / \  |  _ \|  _ \ 
# \ \ /\ / /| |_| | / _ \ | | \___ \ / _ \ | |_) | |_) |
#  \ V  V / |  _  |/ ___ \| |  ___) / ___ \|  __/|  __/ 
#   \_/\_/  |_| |_/_/   \_\_| |____/_/   \_\_|   |_|    
#                                                      
# ____  ____   _    __  __ __  __ _____ ____   __     __  _   _   ____  
# ___||  _ \ / \  |  \/  |  \/  | ____|  _ \  \ \   / / / | / | |___ \ 
#\___ \| |_) / _ \ | |\/| | |\/| |  _| | |_) |  \ \ / /  | | | |   __) |
# ___) |  __/ ___ \| |  | | |  | | |___|  _ <    \ V /   | |_| |_ / __/ 
#|____/|_| /_/   \_\_|  |_|_|  |_|_____|_| \_\    \_/    |_(_)_(_)_____|
#                                                                       
#
#----------------------------------------------------------------------------------------------                                               
# coded by Arijit Bhowmick
#
# 8ae503b206749490f1a2a2b4fe281331903625132f5f207554423c950111fa24
#
#--------------------------------------------------------------------------------------------

#--------------------------------------------------------------------------------------------
#									  MODULES
#--------------------------------------------------------------------------------------------
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
import hashlib
import string
import random
import os
#--------------------------------------------------------------------------------------------

#--------------------------------------------------------------------------------------------------------
#								   Driver Location
#--------------------------------------------------------------------------------------------------------
#
#	geckodriver is a Firefox web driver which is use to operate firefox browser
#	You can download latest geckodriver from https://github.com/mozilla/geckodriver/releases
#	I have provided some geckodriver for Linux, Windows, and Mac for 64bit and 32bit
#--------------------------------------------------------------------------------------------------------
try:
	check_for_log_file=open(os.getcwd()+'driver_location.log', 'r')
	check_driver_rd=check_for_log_file.read()
	check_for_log_file.close()
	try:
		check_driver = open(check_driver_rd, 'r')
		check_driver.close()
	except:
		print('\033[91'+'!!It seems that the driver is not in the location you have previously mentioned!!'+'\033[91')
		driver_not_found='True'
		while driver_not_found=='True':
			driver_location_ask=str(input('\033[32m'+'Please Enter the full location of geckodriver:\n-->> '+'\033[32m'))
			try:
				driver_location_ask_check=open(driver_location_ask,'r')
				driver_location_ask_check.close()
				create_driver_location_log=open(os.getcwd()+'driver_location.log', 'w')
				create_driver_location_log.write(driver_location_ask)
				create_driver_location_log.close()
				driver_not_found='False'
			except:
				print('\033[91m'+'The Location of the geckodriver You have entered is not correct'+'\033[91m')
		

		

except:
	print('\033[91'+'!!It seems that the log file is not created!!!'+'\033[91')
	driver_not_found='True'
	while driver_not_found=='True':
		driver_location_ask=str(input('\033[32m'+'Please Enter the full location of geckodriver:\n-->> '+'\033[32m'))
		try:
			driver_location_ask_check=open(driver_location_ask,'r')
			driver_location_ask_check.close()
			create_driver_location_log=open(os.getcwd()+'driver_location.log', 'w')
			create_driver_location_log.write(driver_location_ask)
			create_driver_location_log.close()
			driver_not_found='False'
		except:
			print('\033[91m'+'The Location of the geckodriver You have entered is not correct'+'\033[91m')
driver_location_read = open(os.getcwd()+'driver_location.log', 'r')
driver_location = driver_location_read.read()
driver_location_read.close()
#--------------------------------------------------------------------------------------------------------

#--------------------------------------------------------------------------------------------------------
#									Information
#--------------------------------------------------------------------------------------------------------

receiver_option_counter='False'
while receiver_option_counter=='False':
	receiver_option = int(input('\033[32m'+'To spam the receiver please select one of the option from below::\n1. Spam huge number of people/group\n2. Spam a single people/group\n\n-->> '+'\033[32m'))
	if receiver_option==1:
		
		receiver_list_ask_condition='False'
		while receiver_list_ask_condition=='False':
			receiver_list_ask = int(input('\033[32m'+'Please select any one option to continue::\n1. Enter the names of the people/groups one by one\n2. Import name of the people/group from file\n\n--> '+'\033[32m'))
			if receiver_list_ask==1:

				receiver_file_list_final=[]
				
				receiver_list_name_1_by_1_complete='False'
				
				while receiver_list_name_1_by_1_complete=='False':
					
					receiver_list_name_1_by_1=str(input('\033[32m'+'\nPlease Enter the name of the people or group\n--> '+'\033[32m'))
					receiver_file_list_final+=[receiver_list_name_1_by_1] 				# Final list of the receivers
					
					ask_for_another_name_info='False'

					while ask_for_another_name_info=='False':
						
						ask_for_another_name=str(input('\033[32m'+'\nDo you want to ener another name? YES(Y) or No(N)'+'\033[32m')).upper()
						
						if ask_for_another_name=='Y':
							receiver_list_name_1_by_1_complete='False'
							ask_for_another_name_info='True'
						elif ask_for_another_name=='N':
							print('The Database is created. The names is/are noted')
							receiver_list_name_1_by_1_complete='True'
							ask_for_another_name_info='True'
							receiver_option_counter='True'
						else:
							ask_for_another_name_info='False'
							print('\033[91m'+'\n!!!You have entered an incorrect option.\nPlease Try again!!!'+'\033[91m')
				Number_of_names=len(receiver_file_list_final)
#-------------------------------------------------------------------------------------------------------------------------------------------
			elif receiver_list_ask==2:
				receiver_from_file_location = str(input('\033[32m'+"\nEnter the Location of the file(containing the name of the people/group) to spam --> "+'\033[32m')) # Location of the file where the names are stored. For example(/home/kali/Desktop/name.txt)
				try:
					receiver_from_file_location_read=open(receiver_from_file_location, 'r')
					receiver_file_list_tempo=list(receiver_from_file_location_read)
					Number_of_names=len(receiver_file_list_tempo)
					receiver_file_list_final=[]
					
					for i in range (Number_of_names):
						Name_tempo=str(receiver_file_list_tempo[i])
						receiver_file_list_final+=[Name_tempo.replace('\n','')]
					receiver_from_file_location_read.close()
					receiver_list_ask_condition='True'
					receiver_option_counter='True'
				except:
					print('\033[91m'+'!!!The file location you have entered is not correct!!!\nPlease Enter it again\n'+'\033[91m')
					print(type(receiver_from_file_location))
					receiver_list_ask_condition='False'
			name_procces = 'receiver_file_list_final'
			break
	elif receiver_option==2:
		receiver_single = input(str('\033[32m'+"Enter the name of the people/group to which you want to spam --> "+'\033[32m')) # Enter the name correctly	
		name_procces = 'receiver_single'
		break
	else:
		print('\033[91m'+'!!!You have entered an incorrect option\nPlease try again\n'+'\033[91m')
		receiver_option_counter='False'

num_times = int(input('\033[32m'+"\nEnter the number of times you want to send --> "+'\033[32m'))
#--------------------------------------------------------------------------------------------------------

#--------------------------------------------------------------------------------------------------------
#					Random SHA512_hashed_string generator (		START	)
#--------------------------------------------------------------------------------------------------------
def random_hash_generator(size=75,chars=string.ascii_uppercase + string.digits):

	random_string=''.join(random.choice(chars) for x in range(size))
	return hashlib.sha512(random_string.encode()).hexdigest()
#--------------------------------------------------------------------------------------------------------
#					Random SHA512_hashed_string generator (		END 	)
#--------------------------------------------------------------------------------------------------------

#--------------------------------------------------------------------------------------------------------
#					Random string generator (		START		)
#--------------------------------------------------------------------------------------------------------
def random_string_generator(size=75,chars=string.ascii_uppercase + string.digits):
    return ''.join(random.choice(chars) for x in range(size))
#--------------------------------------------------------------------------------------------------------
#					Random string generator (		END			)
#--------------------------------------------------------------------------------------------------------

#--------------------------------------------------------------------------------------------------------
#						Type of the thing you want to send
#--------------------------------------------------------------------------------------------------------
choice='False'
while choice=='False':
	choice = int(input('\033[32m'+'\nPlease enter the option to continue\n1. Send a particular message\n2. Send Random Messages(alphabets+number)\n3. Send Hashed Messages(sha256)\n\n--> '+'\033[32m'))
	if choice == 1:
		message = input(str('\033[32m'+'\nType the message you want to send --> '+'\033[32m'))
	elif choice == 2:
		message = random_string_generator()
	elif choice == 3:
		message = random_hash_generator()
	else:
		print('\033[91m'+'\n!!!You have entered an incorrect option please try again!!!'+'\033[91m')
#--------------------------------------------------------------------------------------------------------
#										END
#--------------------------------------------------------------------------------------------------------
print('''\033[34m
 ____  _             _   _                  _   _   _             _    
░██████╗████████╗░█████╗░██████╗░████████╗██╗███╗░░██╗░██████╗░  ░█████╗░████████╗████████╗░█████╗░░█████╗░██╗░░██╗
██╔════╝╚══██╔══╝██╔══██╗██╔══██╗╚══██╔══╝██║████╗░██║██╔════╝░  ██╔══██╗╚══██╔══╝╚══██╔══╝██╔══██╗██╔══██╗██║░██╔╝
╚█████╗░░░░██║░░░███████║██████╔╝░░░██║░░░██║██╔██╗██║██║░░██╗░  ███████║░░░██║░░░░░░██║░░░███████║██║░░╚═╝█████═╝░
░╚═══██╗░░░██║░░░██╔══██║██╔══██╗░░░██║░░░██║██║╚████║██║░░╚██╗  ██╔══██║░░░██║░░░░░░██║░░░██╔══██║██║░░██╗██╔═██╗░
██████╔╝░░░██║░░░██║░░██║██║░░██║░░░██║░░░██║██║░╚███║╚██████╔╝  ██║░░██║░░░██║░░░░░░██║░░░██║░░██║╚█████╔╝██║░╚██╗
╚═════╝░░░░╚═╝░░░╚═╝░░╚═╝╚═╝░░╚═╝░░░╚═╝░░░╚═╝╚═╝░░╚══╝░╚═════╝░  ╚═╝░░╚═╝░░░╚═╝░░░░░░╚═╝░░░╚═╝░░╚═╝░╚════╝░╚═╝░░╚═╝


\033[34m''')
#--------------------------------------------------------------------------------------------------------
#			Open Firefox_Browser and open https://web.whatsapp.com/
#--------------------------------------------------------------------------------------------------------
driver=webdriver.Firefox(executable_path=driver_location)
driver.get("https://web.whatsapp.com/")
#--------------------------------------------------------------------------------------------------------
#										END
#--------------------------------------------------------------------------------------------------------

#--------------------------------------------------------------------------------------------------------
#						Waiting time to scan the QR code
#--------------------------------------------------------------------------------------------------------
driver.implicitly_wait(60)
#--------------------------------------------------------------------------------------------------------

#######################################################################################
#######-------------Condition_for_Multiple/Single_Receiver---------------##############
#######################################################################################

	#######################################################################################
	#######-------------Condition_for_Multiple_Receiver---------------#####################
	#######################################################################################
if name_procces=='receiver_file_list_final':
	for i in range(Number_of_names):
#--------------------------------------------------------------------------------------------------------
#							Xpath of the search_box
#--------------------------------------------------------------------------------------------------------
		search_sender=driver.find_element_by_xpath("/html/body/div[1]/div/div/div[3]/div/div[1]/div/label/div/div[2]")
#--------------------------------------------------------------------------------------------------------

#--------------------------------------------------------------------------------------------------------
#							  Search the Receiver
#--------------------------------------------------------------------------------------------------------
		search_sender.send_keys(receiver_file_list_final[i],Keys.RETURN)
#--------------------------------------------------------------------------------------------------------

#--------------------------------------------------------------------------------------------------------
#							  Xpath of the send_Box
#--------------------------------------------------------------------------------------------------------
		send_box=driver.find_element_by_xpath("/html/body/div[1]/div/div/div[4]/div/footer/div[1]/div[2]/div/div[2]")
#--------------------------------------------------------------------------------------------------------


#--------------------------------------------------------------------------------------------------------
#							    Message Sending
#--------------------------------------------------------------------------------------------------------
		for j in range(num_times):
			send_box.send_keys(message,Keys.RETURN)
#--------------------------------------------------------------------------------------------------------
#									  END
#--------------------------------------------------------------------------------------------------------

	#######################################################################################
	################-------------Condition_for_Single_Receiver---------------##############
	#######################################################################################

#-------------------------------------------------------------------------------------------------------------------
elif name_procces=='receiver_single':


#--------------------------------------------------------------------------------------------------------
#							Xpath of the search_box
#--------------------------------------------------------------------------------------------------------
	search_sender=driver.find_element_by_xpath("/html/body/div[1]/div/div/div[3]/div/div[1]/div/label/div/div[2]")
#--------------------------------------------------------------------------------------------------------

#--------------------------------------------------------------------------------------------------------
#							  Search the Receiver
#--------------------------------------------------------------------------------------------------------
	search_sender.send_keys(receiver_single,Keys.RETURN)
#--------------------------------------------------------------------------------------------------------

#--------------------------------------------------------------------------------------------------------
#							  Xpath of the send_Box
#--------------------------------------------------------------------------------------------------------
	send_box=driver.find_element_by_xpath("/html/body/div[1]/div/div/div[4]/div/footer/div[1]/div[2]/div/div[2]")
#--------------------------------------------------------------------------------------------------------


#--------------------------------------------------------------------------------------------------------
#							    Message Sending
#--------------------------------------------------------------------------------------------------------
	for j in range(num_times):
		send_box.send_keys(message,Keys.RETURN)
#--------------------------------------------------------------------------------------------------------
#									  END
#--------------------------------------------------------------------------------------------------------
#######################################################################################
#####################-------------Condition_for_Error--------------------##############
#######################################################################################
else:
	print('\033[91m'+'!!!An Error occured please contact to the programmer!!!'+'\033[91m')