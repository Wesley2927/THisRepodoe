import java.security.MessageDigest;



class Hash {
    public String sha256(String original) {
    try{
        MessageDigest digest = MessageDigest.getInstance("SHA-256");
        byte[] hash = digest.digest(original.getBytes("UTF-8"));
        StringBuffer hexString = new StringBuffer();

        for (byte b : hash) {
           hexString.append(String.format("%02x", b & 0xff));
        }

        return hexString.toString();
    } catch(Exception e){
       throw new RuntimeException(e);
    }
}
}
    
    
