import json
import boto3
from botocore.exceptions import ClientError

# Configura el cliente DynamoDB
dynamodb = boto3.resource('dynamodb')
tabla = dynamodb.Table('PrestamosLibros')

def lambda_handler(event, context):
    try:
        # Recibe los datos del evento
        usuario_id = event['UsuarioID']  # Ahora con "U" mayúscula
        libro_id = event['LibroID']      # Ahora con "L" mayúscula
        fecha_prestamo = event['fechaPrestamo']
        fecha_devolucion = event['fechaDevolucion']
        estado = event.get('estado', 'activo')  # Estado predeterminado

        # Inserta los datos en la tabla DynamoDB
        tabla.put_item(
            Item={
                'UsuarioID': usuario_id,  # Coincide con DynamoDB
                'LibroID': libro_id,      # Coincide con DynamoDB
                'fechaPrestamo': fecha_prestamo,
                'fechaDevolucion': fecha_devolucion,
                'estado': estado
            }
        )

        return {
            'statusCode': 200,
            'body': json.dumps(f'Datos guardados: {usuario_id} - {libro_id}')
        }

    except ClientError as e:
        return {
            'statusCode': 500,
            'body': json.dumps(f'Error al guardar los datos: {str(e)}')
        }
