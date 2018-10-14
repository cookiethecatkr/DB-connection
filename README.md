# DB-connection
practicing DB connection

/*  #1  */

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class JavaApplication7 {

   public static void main(String[] args) {
        
        Connection conn = null; 
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            conn = DriverManager.getConnection
                    ("jdbc:mysql://localhost:3306/malldb?useSSL=false&serverTimezone=UTC","root","1234");
            System.out.println("데이터베이스에 접속했습니다.");
            conn.close();
        } //try
        catch (ClassNotFoundException cnfe){
            System.out.println("해당 클래스를 찾을 수 없습니다"+cnfe.getMessage());
            
        }
        catch (SQLException se) { 
            System.out.println(se.getMessage()); 
        }
        
        
    }
}


/*  #2  */ 


import java.sql.Connection;
import java.sql.DriverManager;

public class JDBCUtil {

	public static Connection getConnection() {
		try { 
			Class.forName("com.mysql.jdbc.Driver");
			return DriverManager.getConnection("jdbc:mysql://localhost/test", "root", "1234");
		
		} catch(Exception e) {
			e.printStackTrace();
		}
		return null;
	}
}
