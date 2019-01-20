
class encryption:
    """ returns the encrypted form of message and can also decrypt the encrypted form """
    def __init__(self,message):
        self.message=message
    def encrypt(self):
        string=self.message
        import random #importing random module
        enc_list=[]
        iterator=0
        key=[]        
        string_list=[]
        for i in string:
            string_list.append(i)
        for x in range(len(string_list)):
            a=random.randint(100,400) #generating random numbers for key
            enc_num=ord(string_list[iterator])+a 
            enc_list.append(chr(enc_num)) #conversion to random symbols
            key.append(a)
            iterator=iterator+1
        strn='' #empty string to hold encrypted message
        for k in enc_list:
            strn=strn+k
        print(key)
        return strn
    def decrypt(self,encrypted_message,key,password): #data to be passed that has been obtained
        a=12345
        if a!=password:
            print('access denied')
            print('press ok to exit ')
            exit()
        iterator2=0
        dec_list=[]
        enc_list=[]
        for i in encrypted_message:
            enc_list.append(i)
        for i in key:
            y=ord(enc_list[iterator2])-i #conversion to original ascii values
            iterator2=iterator2+1
            c=chr(y) #conversion to actual message
            dec_list.append(c)
        strns='' #empty to string to hold decrypted message
        for l in dec_list:
            strns=strns+l
        return strns
            
