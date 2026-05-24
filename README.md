# ============================================================
#  Universidad Nacional Abierta y a Distancia - UNAD
#  Curso: Fundamentos de Programacion - Codigo: 213022
#  Fase 5 - Evaluacion Final POA
#  Problema 5: Control de horas semanales del equipo
#  Estudiante: Juan Diego Triana Tapiero
#  CC: 1013670847 - Grupo: 213022_741
#  Centro: CEAD Jose Acevedo y Gomez
# ============================================================

# --- CONSTANTE ---
UMBRAL_HORAS = 40

# --- DATOS INICIALES ---
# Matriz: [Nombre, Lunes, Martes, Miercoles, Jueves, Viernes]
matriz_horas = [
    ["Ana Garcia",    9,  8, 10,  7,  9],
    ["Carlos Lopez",  7,  8,  7,  8,  8],
    ["Maria Torres", 10, 10, 10, 10, 10],
    ["Juan Martinez", 6,  7,  8,  9,  8]
]


# --- FUNCION ---
def calcular_horas_y_clasificar(nombre, horas_diarias):
    total_horas = 0
    for horas in horas_diarias:
        total_horas += horas
    if total_horas > UMBRAL_HORAS:
        clasificacion = "Sobretiempo"
    else:
        clasificacion = "Horario Estandar"
    return total_horas, clasificacion


# --- PROGRAMA PRINCIPAL ---
def main():
    print("=" * 55)
    print("   REPORTE SEMANAL DE HORAS - EQUIPO DE TRABAJO")
    print("=" * 55)
    print(f"{'Recurso':<20} {'Total Horas':>12} {'Clasificacion':>18}")
    print("-" * 55)
    for fila in matriz_horas:
        nombre = fila[0]
        horas_diarias = fila[1:]
        total, clasificacion = calcular_horas_y_clasificar(nombre, horas_diarias)
        print(f"{nombre:<20} {total:>12} {clasificacion:>18}")
    print("=" * 55)
    print(f"  Umbral de horas estandar: {UMBRAL_HORAS} horas semanales")
    print("=" * 55)


# --- PUNTO DE ENTRADA ---
if __name__ == "__main__":
    main()
