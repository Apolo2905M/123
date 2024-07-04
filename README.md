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
