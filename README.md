def cambiarcontraseña(lista):
    print ('\nMODIFICAR CONTRASEÑA:')
    Correo = input('Ingresar correo: ')
    Contraseña = input('Ingresar contraseña actual: ')
    k=0
    while k < len(lista):
        if Correo == lista[k].retornaEmail():
            break
        else: k +=1
    if k >= len(lista):
        print('no existe email para cambiar contraseña')
    else:
        if Contraseña == lista[k].getContraseña():
            Contraseña = input('ingresar contraseña Nueva: ')
            lista[k].setContraseña(Contraseña)
            print('contraseña nueva es: {}'.format(lista[k].getContraseña()))
        else: print('ERROR: CONTRASEÑA NO COINCIDE CON LA ACTUAL')
