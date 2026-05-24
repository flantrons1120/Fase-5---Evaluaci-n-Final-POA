# ============================================================
#  Universidad Nacional Abierta y a Distancia - UNAD
#  Curso: Fundamentos de Programación - Código: 213022
#  Fase 5 - Evaluación Final POA
#  Problema 5: Control de horas semanales del equipo
#  Estudiante: Juan Diego Triana Tapiero
#  C.C.: 1013670847 - Grupo: 213022_741
#  Centro: CEAD José Acevedo y Gómez
# ============================================================
 
# --- CONSTANTE ---
UMBRAL_HORAS = 40  # Límite de horas estándar semanales
 
# --- DATOS INICIALES ---
# Matriz: [Nombre del Recurso, Lunes, Martes, Miércoles, Jueves, Viernes]
matriz_horas = [
    ["Ana García",    9,  8, 10,  7,  9],
    ["Carlos López",  7,  8,  7,  8,  8],
    ["María Torres", 10, 10, 10, 10, 10],
    ["Juan Martínez", 6,  7,  8,  9,  8]
]
 
 
# --- MÓDULO / FUNCIÓN ---
def calcular_horas_y_clasificar(nombre, horas_diarias):
    """
    Calcula el total de horas semanales de un recurso
    y clasifica su jornada laboral.
 
    Parámetros:
        nombre (str): Nombre del recurso.
        horas_diarias (list): Lista con horas trabajadas
                              de lunes a viernes.
 
    Retorna:
        total_horas (int): Suma total de horas en la semana.
        clasificacion (str): "Sobretiempo" u "Horario Estándar".
    """
    total_horas = 0
 
    # Estructura repetitiva: sumar horas de cada día
    for horas in horas_diarias:
        total_horas += horas
 
    # Estructura de control: clasificar la jornada
    if total_horas > UMBRAL_HORAS:
        clasificacion = "Sobretiempo"
    else:
        clasificacion = "Horario Estándar"
 
    return total_horas, clasificacion
 
 
# --- PROGRAMA PRINCIPAL ---
def main():
    print("=" * 55)
    print("   REPORTE SEMANAL DE HORAS - EQUIPO DE TRABAJO")
    print("=" * 55)
    print(f"{'Recurso':<20} {'Total Horas':>12} {'Clasificación':>18}")
    print("-" * 55)
 
    # Recorrer cada fila de la matriz
    for fila in matriz_horas:
        nombre        = fila[0]   # Columna 0: nombre del recurso
        horas_diarias = fila[1:]  # Columnas 1 a 5: horas por día
 
        # Llamado al módulo / función
        total, clasificacion = calcular_horas_y_clasificar(nombre, horas_diarias)
 
        # Mostrar resultado de cada recurso
        print(f"{nombre:<20} {total:>12} {clasificacion:>18}")
 
    print("=" * 55)
    print(f"  Umbral de horas estándar: {UMBRAL_HORAS} horas semanales")
    print("=" * 55)
 
 
# --- PUNTO DE ENTRADA ---
if __name__ == "__main__":
    main()
