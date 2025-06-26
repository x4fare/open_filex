# Permissões do OpenFile Plugin

## Permissões Declaradas

### Android 13+ (API 33+)
- `READ_MEDIA_IMAGES` - Apenas para abrir arquivos de imagem
- `READ_MEDIA_VIDEO` - Apenas para abrir arquivos de vídeo  
- `READ_MEDIA_AUDIO` - Apenas para abrir arquivos de áudio

### Android 12 e anterior (API ≤ 32)
- `READ_EXTERNAL_STORAGE` - Limitada por `maxSdkVersion="32"`

### Casos especiais
- `MANAGE_EXTERNAL_STORAGE` - Apenas para arquivos fora do MediaStore em Android 11+

## Justificativa para Google Play

Este plugin precisa dessas permissões para:

1. **Finalidade principal**: Abrir arquivos de mídia com aplicativos externos
2. **Permissões mínimas**: Usa apenas permissões granulares específicas para cada tipo de mídia
3. **Compatibilidade**: Permissão legada limitada a Android 12 e inferior
4. **Transparência**: Usuário sempre é informado sobre que tipo de arquivo será acessado

## Alternativas consideradas

- **Scoped Storage**: Usado sempre que possível
- **MediaStore API**: Preferido para arquivos de mídia
- **FileProvider**: Usado para compartilhamento seguro de arquivos
