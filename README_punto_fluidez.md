# Dashboard · Ensayo N°2: Punto de Fluidez (Pour Point)
## UMSA · Ingeniería Petrolera · PET-212

Dashboard interactivo para la determinación del punto de fluidez de productos derivados del petróleo mediante el método ASTM D-97, con extrapolación para diesel 100% a partir de sistema Diesel-Parafina.

### 📋 Descripción del Ensayo

El punto de fluidez es la temperatura más baja a la cual todavía fluye el fluido bajo condiciones específicas de ensayo. Este parámetro es crítico para el transporte y almacenamiento de combustibles en zonas de bajas temperaturas. El ensayo consiste en enfriar la muestra en un baño frío y examinarla a intervalos de 3°C hasta detectar la temperatura límite de fluidez.

### ✨ Funcionalidades del Dashboard

#### 1️⃣ Identificación de Muestra
- **Sistema Diesel-Parafina**: 3 concentraciones estándar
  - 90% Diesel / 10% Parafina
  - 95% Diesel / 5% Parafina
  - 97% Diesel / 3% Parafina
- Campos personalizables: composición y procedencia

#### 2️⃣ Registro de Datos de Enfriamiento
- Tabla interactiva para ingreso de datos experimentales
- Campos: tiempo (min), T baño hielo (°C), T muestra (°C)
- **Agregar/quitar filas** dinámicamente
- Marcador automático de punto de fluidez observado
- Intervalo recomendado: cada 5 minutos

#### 3️⃣ Curva de Enfriamiento
- Gráfica **Temperatura vs Tiempo**
- Visualización del proceso de enfriamiento
- Marcador del **punto de fluidez** observado
- Identificación del comportamiento térmico de la muestra

#### 4️⃣ Punto de Fluidez Observado
- Selección del índice de dato donde se observó fluidez
- Temperatura de fluidez automática según ASTM D-97
- Intervalo de verificación: 3°C

#### 5️⃣ Extrapolación para Diesel 100%
- **Regresión lineal**: T_fluidez vs % Parafina
- Cálculo automático de pendiente (m) e intercepto (b)
- **Extrapolación** al 0% parafina (diesel puro)
- Gráfica de regresión con:
  - Línea de tendencia
  - Datos experimentales (3 muestras)
  - Punto extrapolado (Diesel 100%)

#### 6️⃣ Resumen y Verificación D.S. 4718
- Comparación con límite normativo: **≤ -1°C**
- Cálculo de error porcentual
- Badge de cumplimiento normativo
- Tabla resumen completa

### 🧪 Metodología del Ensayo

**Preparación:**
1. Formular 3 muestras: 90/10, 95/5, 97/3 (Diesel/Parafina % v/v)
2. Derretir parafina y mezclar homogéneamente
3. Preparar baño frío: hielo + sal + urea (alcanzar -15°C aprox.)

**Procedimiento:**
1. Colocar muestra en frasco de ensayo con termocupla
2. Sumergir en baño frío con aislamiento térmico
3. Registrar temperatura cada 5 minutos
4. Inclinar frasco 45° y observar si fluye (mantener horizontal 5 seg)
5. Continuar enfriando en intervalos de 3°C hasta que **NO** fluya
6. Registrar temperatura de **última observación de fluidez**
7. Repetir con las 3 muestras

**Extrapolación:**
- Graficar: T_fluidez vs % Parafina (3 puntos)
- Regresión lineal: `T = m·(% P) + b`
- Diesel 100%: `T_diesel = b` (cuando % P = 0)

### 📊 Datos Experimentales de Referencia

Según informe Univ. Queso Escobar (UMSA PTQ-715):

| Muestra | % Diesel | % Parafina | T fluidez (°C) |
|---------|----------|------------|----------------|
| M1 | 90 | 10 | 14.9 |
| M2 | 95 | 5 | 9.4 |
| M3 | 97 | 3 | 5.9 |
| **Extrapolado** | **100** | **0** | **0.65** |

**Regresión lineal obtenida:**
- Pendiente m = 1.38 °C/% Parafina
- Intercepto b = 0.65 °C
- R² ≈ 0.99 (ajuste excelente)

**Error vs D.S. 4718:**
- Valor normativo: ≤ -1°C
- Valor experimental: 0.65°C
- Error: 165% (fuera de especificación)

> **Nota**: El diesel de estación de servicio usado en el ensayo **NO cumple** el límite del D.S. 4718, lo que indica posible contaminación con parafinas o necesidad de aditivos pour point depressants.

### 🎯 Normativa Aplicada

- **ASTM D-97**: Método de prueba estándar para punto de fluidez
- **ASTM D-5950**: Método alternativo automatizado
- **D.S. 4718 Bolivia**: Punto de fluidez Diesel ≤ -1°C

### 🚀 Uso del Dashboard

1. **Abrir dashboard**: https://[usuario].github.io/[repositorio]/
2. **Seleccionar muestra**: Click en preset (90/10, 95/5, 97/3)
3. **Registrar datos**: Ingresar temperaturas cada 5 min en la tabla
4. **Identificar punto**: Marcar índice donde se observó fluidez
5. **Ver curva**: Gráfica automática de enfriamiento
6. **Ingresar las 3 muestras**: Completar T fluidez de M1, M2, M3
7. **Extrapolación automática**: Regresión lineal y Diesel 100%
8. **Verificar cumplimiento**: Badge D.S. 4718

### 📱 Compatibilidad

- Funciona **offline** y **online**
- Diseño responsive (desktop y móvil)
- Gráficas Chart.js interactivas
- Tema oscuro optimizado para laboratorio

### 📄 Documentos Adicionales

- **Planilla de laboratorio Word**: Para anotación manual
- **Informe de referencia PDF**: Ejemplo completo con resultados reales

### 🔬 Fórmulas Utilizadas

**Regresión lineal simple:**
```
m = [n·Σ(xy) − Σx·Σy] / [n·Σ(x²) − (Σx)²]
b = [Σy − m·Σx] / n
T_fluidez = m·(% Parafina) + b
```

**Error porcentual:**
```
%E = |T_verdadero − T_experimental| / |T_verdadero| × 100%
```

### ⚠️ Consideraciones Importantes

1. **Baño frío**: Usar hielo + sal + urea para alcanzar temperaturas < -15°C
2. **Aislamiento térmico**: Fibra térmica alrededor del baño para estabilidad
3. **Intervalo 3°C**: Crucial según ASTM D-97
4. **Homogeneización**: Derretir parafina completamente antes de mezclar
5. **Limpieza**: Lavar frascos con solvente entre muestras
6. **Ventilación**: Trabajar en área ventilada (vapores de diesel)

### 🛠️ Tecnologías

- HTML5 + CSS3 + JavaScript vanilla
- Chart.js 4.4.1 (gráficas interactivas)
- Diseño GitHub dark theme
- Cálculo de regresión lineal en JS
- Sin backend requerido

### 📝 Licencia

Uso académico — Universidad Mayor de San Andrés (UMSA)  
Carrera de Ingeniería Petrolera · Refinación del Petróleo PET-212

---

**Desarrollado para**: Estudiantes de Ingeniería Petrolera UMSA  
**Materia**: Refinación del Petróleo PET-212  
**Norma**: ASTM D-97 / D.S. 4718
