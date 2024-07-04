//modelopublicacion

public class Publicacion {
    private int año;
    private String nombreRevista;
    private String titulo;
    
    public Publicacion(int año,String nombreRevista, String titulo){
        this.año=año;
        this.nombreRevista=nombreRevista;
        this.titulo=titulo;
    }
    
    @Override
    public String toString(){
        return this.año+"-"+this.nombreRevista+"-"+this.titulo;
    }
}








//modeloautor

import java.util.ArrayList;
import java.util.List;

public class Autor {
    private int cantidadPublicaciones;
    private String filiacion;
    private String linealInvestigacion;
    private String nacionalidad;
    private String nombre;
    private Publicacion[] publicaciones;
//No se si vale lo de abajo//
    private int cantidadPublicaciones;
    private String filiacion;
    private String lineaInvestigacion;
    private String nacionalidad;
    private String nombre;
    private List<Publicacion> publicaciones;
    private int tamañoArreglo;

    public Autor(String filiacion, String lineaInvestigacion, String nacionalidad, String nombre, int tamañoArreglo) {
        this.cantidadPublicaciones = 0;
        this.filiacion = filiacion;
        this.lineaInvestigacion = lineaInvestigacion;
        this.nacionalidad = nacionalidad;
        this.nombre = nombre;
        this.tamañoArreglo = tamañoArreglo;
        this.publicaciones = new ArrayList<>(tamañoArreglo);
    }

    public void setCantidadPublicaciones(int cantidadPublicaciones) {
        if (cantidadPublicaciones > this.tamañoArreglo) {
            throw new IllegalArgumentException("El número de publicaciones no puede exceder el tamaño del arreglo.");
        }
        this.cantidadPublicaciones = cantidadPublicaciones;
    }

    public void agregarPublicacion(Publicacion publicacionNueva) {
        if (this.cantidadPublicaciones < this.tamañoArreglo) {
            this.publicaciones.add(publicacionNueva);
            this.cantidadPublicaciones++;
        } else {
            throw new IllegalArgumentException("No se pueden agregar más publicaciones, límite alcanzado.");
        }
    }

    @Override
    public String toString() {
        StringBuilder sb = new StringBuilder();
        sb.append("Autor: ").append(nombre).append(" Publicaciones: ");
        for (Publicacion pub : publicaciones) {
            sb.append(pub.toString()).append(" ");
        }
        return sb.toString().trim();
    }
}








