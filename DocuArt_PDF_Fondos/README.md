# 📚 **DocuArt PDF - Sistema de Catalogación Digital**

**Museo de Bellas Artes de Bilbao (MBAB) · Biblioteca Digital**

---

## 🎯 **¿Qué es DocuArt PDF?**

Sistema profesional de catalogación y visualización de fondos artísticos y documentales siguiendo **estándares internacionales**:
- ✅ **ISBD** (Descripción Bibliográfica)
- ✅ **MARC21** (Formato de intercambio)
- ✅ **Encabezamientos de Materia** (Universidad de Sevilla)
- ✅ **CDU** (Clasificación)

---

## 📁 **Estructura de carpetas**

```
proyecto-docuart/
├── index.html              ← Interfaz principal (abrir en navegador)
├── registros.json          ← Base de datos de registros
├── README.md               ← Este archivo
├── pdfs/
│   ├── munoz2018.pdf
│   ├── chillida2016.pdf
│   └── (más PDFs aquí)
└── .gitignore             ← Opcional: para ignorar PDFs en respaldos
```

---

## 🚀 **Cómo usar**

### **1. Descargar y abrir**
- Coloca **todas las carpetas y archivos** en: `T:\Pdf_Catalogar\`
- Abre `index.html` en cualquier navegador (Chrome, Firefox, Edge)

### **2. Buscar y filtrar**
- **Buscador en tiempo real**: Busca por título, autor, resumen, materias
- **Filtros**: Por año y tipo de documento
- **Exportar**: Descarga todos los registros como JSON o CSV

### **3. Visualizar registros**
- Haz clic en cualquier tarjeta para abrir el modal
- Consulta: **ISBD | MARC21 | Materias | Resumen | Documento**
- **Tab "Documento"**: Visor PDF integrado con zoom y navegación

### **4. Descargar PDFs**
- Botón "🔒 Descargar PDF" en el tab "Documento"
- Contraseña: `MBAB` (case-insensitive: mbab, MBAB, MbAb, etc.)

---

## 📊 **Estructura de datos (registros.json)**

Cada registro contiene:

```json
{
  "id": "munoz2018",
  "titulo": "Lucio Muñoz : veinte años",
  "autor": "Muñoz, Lucio (1929-1998)",
  "anio": "2018",
  "lugar": "Madrid",
  "editorial": "Galería Marlborough",
  "tipo": "Catálogo de exposición",
  "paginas": "17",
  "idioma": "es",
  "isbd": "<p>Descripción ISBD normalizada...</p>",
  "marc": "LDR  00000nam a2200000 a 4500\n...",
  "materias": [
    "Muñoz, Lucio, 1929-1998 -- Catálogos de exposiciones",
    "Pintura española -- Siglo XX -- Catálogos de exposiciones"
  ],
  "resumen": "Resumen de ~300 palabras...",
  "cdu": "759.6",
  "pdf": "munoz2018.pdf",
  "ocr_verificado": true,
  "fecha_catalogacion": "2024-08-11",
  "catalogador": "Jomana"
}
```

---

## 🔄 **Flujo de catalogación**

### **Cuando Jomana sube un PDF:**

1. **Jomana proporciona:**
   - Archivo PDF
   - Metadatos básicos (si no están en portada)

2. **Claude (yo) genero automáticamente:**
   - ✅ Descripción ISBD (normalizada)
   - ✅ Registro MARC21 (completo)
   - ✅ Encabezamientos de Materia (Universidad de Sevilla)
   - ✅ Resumen (~300 palabras, profesional)
   - ✅ CDU (clasificación)
   - ✅ OCR verificado (sí/no)

3. **Resultados:**
   - Actualizo `registros.json` con el nuevo registro
   - Coloco PDF en carpeta `/pdfs/`
   - Jomana verifica en navegador
   - **✅ Listo**

---

## 🎨 **Características principales**

### **Búsqueda y filtros**
- 🔍 Búsqueda en tiempo real (título, autor, resumen, materias)
- 📅 Filtro por año
- 📋 Filtro por tipo de documento
- 📊 Contador de resultados

### **Visor PDF integrado**
- 📄 Ver PDFs sin descargar
- 🔍 Zoom in/out
- ➡️ Navegación de páginas
- 🔒 Descarga protegida con contraseña

### **Exportación**
- 📥 Descargar como JSON (respaldo profesional)
- 📥 Descargar como CSV (Excel/Sheets)

### **Metadatos profesionales**
- 📌 ISBD (descripción bibliográfica)
- 🏷️ MARC21 (estándar de intercambio)
- 🎨 Encabezamientos de Materia (Sevilla)
- 📚 CDU (clasificación)
- 👤 Catalogador y fecha de catalogación

---

## 🔐 **Contraseña de descarga**

- **Usuario:** No requiere
- **Contraseña:** `MBAB` o `mbab` (case-insensitive)
- **Ubicación:** En cada registro, tab "Documento"

---

## 📝 **Notas técnicas**

### **Navegadores soportados**
- ✅ Chrome/Chromium (recomendado)
- ✅ Firefox
- ✅ Edge
- ✅ Safari

### **Funciona offline**
- ✅ Sí, funciona completamente sin conexión a internet
- Solo necesita los archivos locales

### **Responsivo**
- ✅ Funciona en desktop, tablet y móvil
- Interfaz adaptable a todos los tamaños

### **Sin base de datos**
- ✅ No requiere servidor
- ✅ Solo JSON + HTML + JavaScript
- ✅ Fácil de respaldar y transferir

---

## 🛠️ **¿Cómo añadir nuevos registros?**

**Opción A: Claude lo hace (RECOMENDADO)**
1. Envía PDF a Claude
2. Claude genera automáticamente todos los metadatos
3. Verifica en navegador

**Opción B: Edición manual (si es necesario)**
1. Abre `registros.json` con un editor de texto
2. Copia la estructura de un registro existente
3. Completa los campos
4. Guarda el archivo
5. Recarga `index.html` en navegador

---

## 📞 **Contacto y soporte**

**Proyecto:** DocuArt PDF  
**Cliente:** Museo de Bellas Artes de Bilbao (MBAB)  
**Biblioteca:** Fondos artísticos y documentales  
**Responsable:** Jomana  
**Gestión técnica:** Claude (Anthropic)

---

## 📋 **Checklist de implementación**

- [x] Estructura de carpetas creada
- [x] Base de datos `registros.json` (2 registros ejemplo)
- [x] Interfaz `index.html` (diseño profesional)
- [x] Visor PDF integrado (PDFjs)
- [x] Búsqueda en tiempo real
- [x] Filtros (año, tipo)
- [x] Exportación JSON/CSV
- [x] Contraseña de descarga (MBAB)
- [x] Metadatos de catalogación (fecha, catalogador)
- [x] Documentación (este README)

---

## 🚀 **Próximos pasos**

1. ✅ Descarga todos los archivos
2. ✅ Coloca en `T:\Pdf_Catalogar\`
3. ✅ Abre `index.html` en navegador
4. ✅ Verifica funcionamiento
5. ✅ Envía primer PDF a Claude para catalogar

---

**Versión:** 1.0  
**Fecha:** 11 de agosto de 2024  
**Estado:** ✅ Listo para usar

