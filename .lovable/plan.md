# Exclusão completa e proteção de dados

## Resultado
- Substituir a exclusão aparente por uma exclusão definitiva disponível somente para administradores.
- Ao excluir um cliente, apagar em conjunto processos, beneficiários, histórico, registros de documentos e os arquivos privados vinculados.
- Manter cadastro manual, importação por PDF, busca e edição funcionando.
- Reforçar a proteção de senhas e dados pessoais de clientes e colaboradores.

## Implementação
1. Criar uma operação protegida no servidor que confirme o perfil de administrador, reúna os arquivos do cliente, remova-os do armazenamento privado e só então apague o cliente e seus dados relacionados.
2. Usar as relações existentes com exclusão em cascata para processos, beneficiários, histórico e registros de documentos; tornar a operação verificável para evitar confirmações falsas.
3. Trocar o botão atual de exclusão pela operação protegida e atualizar o aviso para deixar claro que a remoção é irreversível.
4. Confirmar e documentar que senhas continuam sob o sistema de autenticação, onde são armazenadas como hashes seguros e nunca como texto legível.
5. Proteger CPF, telefone, e-mail, endereço e demais dados pessoais com criptografia no lado do servidor, mantendo índices derivados não reversíveis apenas onde a busca e a detecção de duplicidade exigirem.
6. Migrar os dados existentes antes de remover valores legíveis, sem expor a chave de criptografia ao navegador.
7. Revisar permissões, executar a análise de segurança e validar cadastro, consulta, edição e exclusão completa em uma conta administrativa.

## Segurança e limites
- A chave de criptografia ficará somente no ambiente protegido do servidor.
- Administradores e colaboradores ativos continuam sujeitos às permissões atuais; criptografia não substituirá as regras de acesso.
- A exclusão de cliente será permanente e não terá recuperação pelo CRM.
