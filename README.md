# Desafio-AWS-Step-Functions-
Repositório modelo para estudos e futuras implementações com AWS Step Functions, contendo exemplos de máquinas de estado (ASL), handlers (Lambda)

def lambda_handler(event, context):
    payload = event.get('Payload') if isinstance(event, dict) and 'Payload' in event else event
    data = payload.get('body') if isinstance(payload, dict) else payload

    if not data or 'id' not in data:
        raise Exception('missing-id')

    return {
        'status': 'ok',
        'validated': True,
        'input': data
    }
aws-stepfunctions-python-demo/

README.md
 state-machines/
   sequential-flow.asl.json
lambdas/
    validate_handler/
       index.py
    process_handler/
     index.py
     notify_handler/
        index.py

