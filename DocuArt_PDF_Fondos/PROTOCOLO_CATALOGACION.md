# 📋 **PROTOCOLO DE CATALOGACIÓN - DocuArt PDF**

**Museo de Bellas Artes de Bilbao (MBAB)**  
**Biblioteca Digital de Fondos Artísticos**

---

## 🎯 **Objetivo**

Establecer un procedimiento claro, normalizado y profesional para la catalogación de fondos artísticos y documentales siguiendo **estándares internacionales**.

---

## 📚 **Estándares aplicables**

| Estándar | Propósito | Aplicación |
|----------|----------|-----------|
| **ISBD** | Descripción bibliográfica normalizada | Presentación de metadatos |
| **MARC21** | Intercambio de datos bibliográficos | Base de datos estructurada |
| **Encabezamientos Sevilla** | Indización temática | Materias de búsqueda |
| **CDU** | Clasificación temática | Organización sistemática |
| **OCR** | Reconocimiento de caracteres | Búsqueda en texto completo |

---

## 🔄 **FLUJO DE TRABAJO**

### **Fase 1: Recepción de PDF**

**Jomana envía:**
- ✅ Archivo PDF
- ✅ Metadatos básicos (si existen dudas en portada)

**Información requerida:**
- Autor/Responsable principal
- Título
- Año de publicación
- Lugar de edición
- Editorial
- Número de páginas
- Tipo de documento
- Idioma

---

### **Fase 2: Análisis y Extracción**

**Claude (catalogador automático):**

1. **Lectura del PDF**
   - Portada completa
   - Colofón (lugar, editorial, año)
   - Índice (si existe)
   - Primeras páginas
   - Últimas páginas

2. **Identificación de elementos**
   - Autor/Responsable
   - Título principal y subtítulos
   - Edición
   - Editorial
   - Año exacto
   - Número de páginas
   - Ilustraciones/material especial
   - Idioma
   - Tipo documental

3. **OCR y búsqueda**
   - Verificar si PDF es texteable
   - Aplicar OCR si es necesario
   - Limpiar y optimizar

---

### **Fase 3: Generación de registros**

**Información a generar:**

#### **A) DESCRIPCIÓN ISBD**
```
Estructura normalizada según ISBD (Norma Internacional de Descripción Bibliográfica)

Ejemplo:
Autor. – Título : subtítulo / responsable. – Lugar : Editorial, año.
Páginas : tipo de ilustraciones ; formato.
Nota sobre contenido y contexto.
```

**Elementos obligatorios:**
- Responsable principal (autor/editor)
- Título (en mayúsculas iniciales)
- Subtítulo (si existe)
- Mención de responsabilidad (traductores, ilustradores, comisarios)
- Lugar de publicación
- Editorial
- Año de publicación
- Descripción física (páginas, ilustraciones, dimensiones)
- Nota de contenido

---

#### **B) REGISTRO MARC21**

**Estructura de campos aplicables:**

| Campo | Descripción | Obligatorio |
|-------|-------------|------------|
| LDR | Líder | ✅ Sí |
| 008 | Datos de longitud fija | ✅ Sí |
| 040 | Fuente catalogación | ✅ Sí |
| 100/110 | Responsable principal | ✅ Sí (si existe) |
| 245 | Título | ✅ Sí |
| 260 | Publicación | ✅ Sí |
| 300 | Descripción física | ✅ Sí |
| 650 | Encabezamientos temáticos | ✅ Sí |
| 655 | Tipo de documento | ✅ Sí |

**Indicadores y subcampos:**
- Aplicar correctamente según MARC21
- Usar subcampos ($a, $b, $c, etc.)
- Indicadores de control (primer/segundo carácter)

---

#### **C) ENCABEZAMIENTOS DE MATERIA**

**Fuente:** Universidad de Sevilla (SIBIUS)  
**URL:** https://biblus.us.es/bib2/embus/embusUsuario/

**Proceso:**
1. Identificar temas principales (máximo 4-6)
2. Buscar en SIBIUS
3. Usar forma autorizada exacta
4. Respetar subdivisiones geográficas/cronológicas

**Ejemplo:**
- ❌ Incorrecto: "Pintura española del siglo veinte"
- ✅ Correcto: "Pintura española -- Siglo XX"

**Temas típicos en catálogos de arte:**
- Artista: `Apellido, Nombre, fechas -- Catálogos de exposiciones`
- Técnica: `Pintura sobre madera`, `Escultura abstracta`
- Período: `Siglo XX`, `Arte moderno`
- Corriente: `Informalismo (Arte)`, `Cubismo`
- Geografía: `España`, `Europa`

---

#### **D) CLASIFICACIÓN CDU**

**Sistema:** Clasificación Decimal Universal

**Ejemplos comunes en arte:**
- `759.6` = Pintura española
- `733` = Escultura moderna
- `700s` = Arte en general
- `770s` = Fotografía
- `780s` = Música

**Obtención:**
- Consultables en tablas CDU estándar
- Reflejar tema principal del documento

---

#### **E) RESUMEN**

**Extensión:** ~250-300 palabras (profesional)

**Contenido:**
- Contexto histórico/artístico
- Contenido principal
- Temas tratados
- Relevancia/importancia

**Tono:** Académico, objetivo, accesible

**Estructura recomendada:**
1. Frase introductoria (qué es, cuándo, dónde)
2. Desarrollo (contenido, temas, autores)
3. Conclusión (relevancia, público objetivo)

**Ejemplo:**
> "Catálogo de la exposición 'Buscando la luz. Chillida' celebrada en el Museo Regional de Arte Moderno de Cartagena (mayo-agosto de 2016). El proyecto fue comisariado por Ignacio Chillida Belzunce, hijo del artista, y reúne una selección representativa de la obra escultórica de Eduardo Chillida, con especial énfasis en la relación entre la forma, el espacio y la luz. Acompañado de ensayos críticos que analizan la evolución artística de Chillida y su influencia en la escultura moderna española e internacional."

---

#### **F) OCR VERIFICADO**

**Valores:**
- `true` = PDF completamente texteable (búsqueda de texto funciona)
- `false` = PDF escaneado (requiere OCR manual)

**Proceso:**
- Abrir PDF en navegador
- Intentar seleccionar/copiar texto
- Registrar resultado

---

#### **G) METADATOS DE CATALOGACIÓN**

**Información de auditoría:**
- `fecha_catalogacion` = "YYYY-MM-DD" (fecha cuando se registró)
- `catalogador` = "Jomana" (responsable)

---

## ✅ **LISTA DE VERIFICACIÓN POR REGISTRO**

Antes de confirmar cada catalogación:

- [ ] **ID único** (sin espacios, en minúsculas)
- [ ] **Título completo y exacto**
- [ ] **Autor/Responsable identificado**
- [ ] **Año de publicación correcto**
- [ ] **Lugar de edición verificado**
- [ ] **Editorial correcta**
- [ ] **Tipo de documento clasificado**
- [ ] **Número de páginas exacto**
- [ ] **Idioma identificado**
- [ ] **ISBD bien estructurada**
- [ ] **MARC21 con indicadores correctos**
- [ ] **Encabezamientos Sevilla validados** (máximo 6)
- [ ] **CDU asignada correctamente**
- [ ] **Resumen ~300 palabras, profesional**
- [ ] **OCR verificado (sí/no)**
- [ ] **PDF comprimido y optimizado** (si necesario)
- [ ] **Archivo PDF en carpeta /pdfs/**
- [ ] **Metadatos de catalogación completos**

---

## 📁 **NOMBRAMIENTO DE ARCHIVOS**

**Formato:** `apellido+anio.pdf`

**Ejemplos:**
- ✅ `munoz2018.pdf`
- ✅ `chillida2016.pdf`
- ✅ `morellon1995.pdf`
- ❌ `documento_importante.pdf`
- ❌ `Catalogo de Exposicion.pdf`

**Reglas:**
- Solo minúsculas
- Solo letras y números
- ID del registro = mismo nombre (sin .pdf)

---

## 🔐 **COMPRESIÓN DE PDFs**

**¿Cuándo comprimir?**
- Archivo > 10 MB
- Múltiples imágenes de alta resolución
- Necesidad de archivar eficientemente

**Herramientas recomendadas:**
- Online: `ilovepdf.com` (Compress PDF)
- Windows: `7-Zip`, `WinRAR`
- Software: `Adobe Acrobat Pro`

**Calidad mínima recomendada:**
- ✅ Texto legible
- ✅ Imágenes visuales pero comprimidas
- ✅ Tamaño <50% original (si posible)

**Verificación post-compresión:**
- Probar lectura en navegador
- Confirmar OCR sigue siendo válido

---

## 🎯 **CONTROL DE CALIDAD**

### **Validación por Jomana:**

1. **En navegador (index.html)**
   - ✅ Registro aparece en búsqueda
   - ✅ Tarjeta muestra datos correctos
   - ✅ Modal abre sin errores
   - ✅ ISBD se ve bien formateado
   - ✅ MARC21 se ve legible
   - ✅ Materias son relevantes
   - ✅ Resumen es coherente
   - ✅ Visor PDF funciona
   - ✅ Descarga con contraseña funciona
   - ✅ Exportación CSV/JSON funciona

2. **En datos (registros.json)**
   - ✅ JSON válido (sin errores de sintaxis)
   - ✅ Todos los campos completados
   - ✅ Fechas en formato YYYY-MM-DD
   - ✅ Booleanos correctos (true/false)

3. **Archivos PDF**
   - ✅ Archivo existe en `/pdfs/`
   - ✅ Nombre coincide con registro
   - ✅ Peso optimizado (si fue comprimido)
   - ✅ Legible en visor

---

## 📊 **ESTADÍSTICAS Y AUDITORÍA**

**Datos registrados automáticamente:**
- Total de registros catalogados
- Registros por año
- Registros por tipo
- OCR verificados vs pendientes
- Catalogador responsable
- Fechas de catalogación

**Útil para:** Reportes, auditoría, análisis de colección

---

## 🔄 **REVISIÓN Y ACTUALIZACIONES**

**Procedimiento:**
1. Jomana identifica error/cambio necesario
2. Comunica a Claude
3. Claude actualiza `registros.json`
4. Jomana verifica en navegador
5. Confirmación

**No es necesario:**
- Editar HTML
- Modificar código
- Tocar archivos .js

---

## ✨ **BUENAS PRÁCTICAS**

✅ **Hacer:**
- Descripción minuciosa en ISBD
- Resúmenes objetivos y profesionales
- Encabezamientos precisos (Sevilla)
- Nomenclatura consistente de archivos
- Respaldos periódicos de registros.json
- Verificación en navegador antes de confirmar

❌ **No hacer:**
- Editar código HTML/JavaScript
- Cambios sin verificación previa
- Resúmenes muy cortos o vagos
- Encabezamientos inventados
- Dejar PDFs sin optimizar (>50MB)
- Faltar metadatos de catalogación

---

## 📞 **COMUNICACIÓN CON CLAUDE**

**Formato estándar para enviar PDF:**

1. PDF completo
2. Información básica (si hay dudas):
   - Autor
   - Año exacto
   - Lugar edición
   - Editorial
   - Tipo documento
3. Notas especiales (si existen)

**Claude responde con:**
- Todos los metadatos generados
- Vista previa de cómo se vería en la interfaz
- Solicitud de confirmación
- Una vez confirmado: actualiza sistema

---

## 📈 **ESCALABILIDAD**

**Actualmente:** <500 registros (óptimo)

**Sistema soporta:**
- ✅ Búsqueda rápida
- ✅ Exportación sin problemas
- ✅ Navegación fluida
- ✅ Respaldo fácil

**Si crece >1000 registros:** Considerar bases de datos reales (PostgreSQL, etc.)

---

## 📝 **Versión y control**

**Versión:** 1.0  
**Fecha:** 11 de agosto de 2024  
**Responsable:** Jomana + Claude  
**Próxima revisión:** Según sea necesario

---

**FIN DEL PROTOCOLO**

