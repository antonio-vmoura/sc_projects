# Trabalho 01

Trabalho 01 consistiu na implementação da cifra de Vigenère. A cifra de Vigenère é uma técnica de criptografia que usa uma série de diferentes cifras de César baseadas nas letras de uma palavra-chave. Este trabalho envolveu a criação de funções para cifrar e decifrar textos utilizando esta técnica, além de explorar suas propriedades e limitações.

# Trabalho 02

## Lado A (Emissor)
1. **Gerar Chaves RSA**
    - Checar primalidade dos números p e q, cada um com 1024 bits, usando Miller-Rabin.
2. **Gerar Chave de Sessão** 
    - Chave de sessão de 128 ou 256 bits.
3. **Cifrar Documento**
    - Cifrar simetricamente (AES) o documento com a chave de sessão.
4. **Cifrar Chave de Sessão**
    - Cifrar assimetricamente (RSA) a chave de sessão usando a chave pública do receptor e OAEP.
5. **Assinatura Digital**
    - Calcular o hash do documento não cifrado.
    - Cifrar o hash do documento com a chave privada do emissor.
6. **Enviar**
    - Chave de sessão cifrada assimetricamente + IV.
    - Documento cifrado simetricamente.
    - Hash cifrado (assinatura) assimetricamente.

## Lado B (Receptor)
1. **Decifrar Chave de Sessão**
    - Decifrar a chave de sessão com a chave privada do receptor.
2. **Decifrar Documento**
    - Decifrar o documento com a chave de sessão decifrada.
3. **Verificar Integridade**
    - Calcular o hash do documento decifrado.
    - Decifrar a assinatura (hash cifrado) com a chave pública do emissor.
    - Comparar os hashes.