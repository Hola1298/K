import tkinter as tk

# Crear ventana principal
ventana = tk.Tk()
ventana.geometry("400x300")
ventana.title("Cálculo de términos de sucesión aritmética")
ventana.config(bg="#262626")

def calcular_termino():
    # Obtenemos los valores de a, d y n desde las cajas de texto
    a = float(caja_a.get())
    d = float(caja_d.get())
    n = int(caja_n.get())

    # Calculamos el término de la sucesión aritmética
    termino = a + (n - 1) * d

    # Mostramos el resultado en la etiqueta correspondiente
    resultado.config(text=f"El término {n} de la sucesión es: {termino}")
    
# Crear marco para los elementos de entrada
marco_entrada = tk.Frame(ventana, bg="#262626")
marco_entrada.pack(pady=10)

# Crear etiquetas y entradas para los valores de la sucesión
tk.Label(marco_entrada, text="Primer término:", fg="white", bg="#262626").grid(row=0, column=0, pady=5, padx=10)
caja_a = tk.Entry(marco_entrada, bg="#FFC107", fg="black")
caja_a.grid(row=0, column=1, pady=5, padx=10)

tk.Label(marco_entrada, text="Diferencia:", fg="white", bg="#262626").grid(row=1, column=0, pady=5, padx=10)
caja_d = tk.Entry(marco_entrada, bg="#FFC107", fg="black")
caja_d.grid(row=1, column=1, pady=5, padx=10)

tk.Label(marco_entrada, text="Término n a encontrar:", fg="white", bg="#262626").grid(row=2, column=0, pady=5, padx=10)
caja_n = tk.Entry(marco_entrada, bg="#FFC107", fg="black")
caja_n.grid(row=2, column=1, pady=5, padx=10)

# Crear botón de cálculo
boton_calcular = tk.Button(ventana, text="Calcular término", bg="#FFC107", fg="black", command=calcular_termino)
boton_calcular.pack(pady=10)

# Crear etiqueta para mostrar resultado
resultado = tk.Label(ventana, text="", bg="#262626", fg="white", font=("Helvetica", 14))
resultado.pack(pady=10)

# Ejecutar la ventana
ventana.mainloop()
