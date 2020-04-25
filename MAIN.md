from ClaseEmail import EMAIL

import manejadorEmail

import csv


if __name__ == '__main__':
    archivo=open('conjuntoEmail.csv')
    reader=csv.reader(archivo,delimiter=',')
    listadeEmails = []
    for fila in reader:
        print(fila)
    unemail= EMAIL()
    unemail.testEmail(fila,listadeEmails)
    for i in range(len(listadeEmails)):
        print (listadeEmails[i].retornaEmail())    
    print ('INGRESAR NOMBRE, CORREO Y CONTRASEÑA DE CORREO')
    Nombre = input('NOMBRE: ')
    Correo = input('CORREO: ')
    Contraseña = input('CONTRASEÑA: ')
    unemail.crearcuenta(Correo,Contraseña)
    listadeEmails.append(unemail)
    print('estimado {} te enviaremos tus mensajes a la direccion {}'.format(Nombre,listadeEmails[len(listadeEmails)-1].retornaEmail()))
    manejadorEmail.cambiarcontraseña(listadeEmails)
    contador=0
    undominio= input('Ingresar Dominio a verificar: ')
    for i in range(len(listadeEmails)):
        if listadeEmails[i].getDominio() == undominio:
            contador += 1
    print('la cantidad de dominios: {} es de: {}'.format(undominio,contador))
