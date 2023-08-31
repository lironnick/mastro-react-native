# APP com LIB `MAESTRO` TESTE

## APP

Iniciar o APP

```CMD
    yarn start
```

## MAESTRO

Instalar a `CLI` do `MAESTRO`

### Criar Arquivo para executar teste `test.yaml`

```YARML
    appId: com.lironnick.maestro
    env:
    EMAIL: "lironnick@gmail.com"
    PASSWORD: "123"
    ---
    - openLink: exp://10.0.0.143:8081
    - tapOn:
        id: input-email
    - inputText: ${EMAIL}

    - tapOn:
        id: input-password
    - inputText: ${PASSWORD}
    - hideKeyboard

    - tapOn:
        id: button-entrar

    - assertVisible: 'Acesso Liberado!'


```

### executar teste

O `-e` é para passar uma valor para variavel de ambiente

```CMD
    maestro test -e EMAIL=lironnick@gmail.com -e PASSWORD=123  test.yaml
```

```CMD
    maestro test test.yaml
```

Para ele gravar a tela e gerar um video do teste

```CMD
    maestro record test.yaml
```
