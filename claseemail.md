class EMAIL:
    __idCuenta=''
    __Dominio=''
    __TipoDominio=''
    __Contraseña=''
    
    def __init__(self,idc='',dom='',tipdom='',paswd=''):
        if isinstance(idc,str):
            self.__idCuenta= idc
        if isinstance(dom,str):
            self.__Dominio= dom
        if isinstance(tipdom,str):
            self.__TipoDominio= tipdom
        if isinstance(paswd,str):
            self.__Contraseña= paswd
    def __str__(self):
        return '({},{},{},{})'.format(self.__idCuenta, self.__Dominio, self.__TipoDominio, self.__Contraseña)
    def retornaEmail(self):
        mailcompleto = self.__idCuenta + '@' + self.__Dominio +  '.' + self.__TipoDominio
        return mailcompleto
    def getDominio(self):
        return self.__Dominio
    def getContraseña(self):
        return self.__Contraseña
    def setContraseña(self,pasw):
        self.__Contraseña = pasw
    def crearcuenta (self,cuenta,contr=''):
        if isinstance(cuenta,str):
            separador = '@'
            separadorpto= '.'
            separado= cuenta.split(separador)
            separadoporpunto= separado[1].split(separadorpto)
            self.__idCuenta = separado[0]
            self.__Dominio = separadoporpunto[0]
            self.__TipoDominio = separadoporpunto[1]
            if isinstance(contr,str):
                self.__Contraseña = contr
            else:
                    print('contraseña no es de tipo string')
        else:
            print ('la cuenta ingresada no es de tipo string')
    
    def testEmail(self,fila,lista):
        for i in range(len(fila)):
            e1= EMAIL()
            e1.crearcuenta(fila[i])
            lista.append(e1)
