---
layout: post
title: Habilitando chamadas SIP/VoIP nativo no Motorola Moto G
comments: true
---

O celular Motorola Moto G por padrao nao permite fazer chamadas pela internet usando SIP/VoIP.

Com esse guia iremos habilitar esse tipo de chamada sem termos que instalar nenhum app para isso.

Os requisitos basicos sao:

- Bootloader desbloqueado
- Root
- Um gerenciador de arquivos com permissoes root

Uma vez que seu sistema esteja pronto, navegue ate a pasta

> /system/etc/permission

e abra o arquivo

> android.software.sip.xml

no final do arquivo, onde diz

{% highlight xml %}
<permissions>
	<feature name="android.software.sip" />
</permissions>
{% endhighlight %}

adicione uma linha para que fique da seguinte forma

{% highlight xml %}
<permissions>
	<feature name="android.software.sip" />
	<feature name="android.software.sip.voip"/>
</permissions>
{% endhighlight %}

Salve o arquivo e reinicie o celular.

Para configurar seu servico VoIP abra a tela para fazer chamada, abra o menu e selecione configuracoes de chamada. Em configuracoes de chamadas de internet configure sua conta.

Configure tambem quando voce quer ser perguntado para fazer chamadas usando seu servico VoIP.

Pronto, agora voce pode selecionar chamadas pela internet quando ligar para alguem.
