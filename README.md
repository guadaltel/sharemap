# M.plugin.ShareMap

Plugin que permite copiar la url del mapa actual visualizado.
Exporta la información de todas las capas cargadas en el mapa.

![Imagen1](./img/shareMap_1.png)

## Dependencias

- sharemap.ol.min.js
- sharemap.ol.min.css


```html
 <link href="../../plugins/sharemap/sharemap.ol.min.css" rel="stylesheet" />
 <script type="text/javascript" src="../../plugins/sharemap/sharemap.ol.min.js"></script>
```

## Parámetros

El constructor se inicializa con un JSON de _options_ con los siguientes atributos:


- **baseUrl**. Url sobre la que está montada la instancia de mapea del tipo https://cnigvisores_pub.desarrollo.guadaltel.es/mapea/
- **title**. Título para la cabecera de la ventana (Por defecto 'Compartir Mapa'
- **btn**. Título para el botón Aceptar (Por defecto 'Aceptar')
- **copyBtn**. Título para el botón copiar (Por defecto 'Copiar url')
- **tooltip**. Texto para el mensaje cuando se copia la cadena (Por defecto 'Copiado')
- **overwriteStyles**. Indica si se le quieren pasar estilos adicionales (Por defecto false)
- **styles**. Estilo a aplicar para sobreescribir
  - **Ejemplo**
```javascript
'styles': {
 *  'primaryColor': 'yellow',
 *  'secondaryColor': 'green'
 *  }
```

- **position**. Indica la posición donde se mostrará el plugin
  - 'TL':top left (default)
  - 'TR':top right 
  - 'BL':bottom left 
  - 'BR':bottom right

## Parámetros API REST
```
URL_API?sharemap=baseUrl*position*title*tooltip*btn*copyBtn
````
Ejemplo:
```html
http://cnig-api-core.desarrollo.guadaltel.es/api-core/?sharemap=http://cnig-api-core.desarrollo.guadaltel.es/api-core/*BL*Compartir URL*Copiado*Aceptar*Copiar
```
## Eventos

## Otros métodos


## Ejemplos de uso
### Ejemplo 1

```javascript
   const map = M.map({
     container: 'map'
   });
  
   const mp = new M.plugin.ShareMap({
      postition: 'TL',
   });

   map.addPlugin(mp);
```
