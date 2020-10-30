# PruebaMySQL
package pruebamysql;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.util.Properties;
/**
 *
 * @author HP
 */
public class PruebaMySQL {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
        //conecciones 
        Connection conexion1 = null;
        Connection conexion2 = null;
        Connection conexion3 = null;
        
        //usuario y clave
        String user = "root";
        String password = "";
        
        try {
            
            //una sola cadena de coneccion, es un solo parametro se conecta el
            //usuario y el pasword
            String ur11 = "jdbc:mysql://localhost:3306/mibase?user=" + "&pasword=" + password;
            conexion1 = DriverManager.getConnection(ur11);
           
         if (conexion1 != null){
            System.out.println("conexion 1: conexion a mi base satisfactoria");
        }  
                    // se envia la cadena y los datos de usuario y password por separadp
          Properties datos = new  Properties();
          datos.put("password", password);
          datos.put("user", user);
          String ur12 = "jdbc:mysql://localhost:3306/mibase";
          conexion2 = DriverManager.getConnection(ur12, datos);
          
          if (conexion2 != null){
              System.out.println("conexion 2: conexion a mi base satisfactoria");
          }
          
          // se envia la cadena, el usuario y el password por separado
          String ur13 = "jdbc:mysql://localhost:3306/mibase";
           conexion3 = DriverManager.getConnection(ur13, datos, password);
           
            if (conexion3 != null){
              System.out.println("conexion 3: conexion a mi base satisfactoria");
          }
            catch (SQLException e){
            System.out.println("Error, verifique su usuario o password o nonmbre de la base de datos");
            e.printStackTrace();
      }
    }
  }
}
      
