package net.codejava;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
public class sqlite {

	public static void main(String[] args) {
		String jdbcUrl = "jdbc:sqlite:/E:\\sqlite-tools-win32-x86-3360000\\userdb.db";
	    try {
	     	Connection connection = DriverManager.getConnection(jdbcUrl);
	        String sql = "SELECT * FROM movies";
	     
	        Statement statement = connection.createStatement();
 	        ResultSet result = statement.executeQuery(sql);
 	        
 	        Statement st = connection.createStatement();
 	        ResultSet rs = st.executeQuery( "SELECT actor FROM movies WHERE movie ='kgf'" );
 	      
 	        while (result.next()) {
 	        	String movie = result.getString("movie" );
 	        	String actor = result.getString("actor" );
 	        	String actress = result.getString("actress" );
 	        	String director = result.getString("director" );
 	        	String year_of_release = result.getString("year_of_release" );
 	        
 	        	System.out.println(movie + "|" + actor + "|" +  actress + "|" + director + "|" + year_of_release );

 	        	
 	        
 	        }
 	        
 	       while (rs.next()) {
	        	String movie = rs.getString("actor" );
	        	System.out.println(movie );
	        			
 	       }
 	        
	    } catch (SQLException e ) {
	    	System.out.println("Error connecting to sqlite database");
	        e.printStackTrace();
	    }
	    
	    
	    
	    
	    
	    
	    
	    }

}
