public class Book2 {
    public String title;
    public String author;
    public int yearPublished;


    public Book(String title, String author, int yearPublished) {
        this.title = title;
        this.author = author;
        this.yearPublished = yearPublished;
    }


    public String getBookInfo() {
        return "This" + title + "by" + author + "and published in" + yearPublished;
    }

    public void printBookDetails() {
        System.out.println(getBookInfo());
    }
}


class PrintedBook extends Book{
    private int numberOfPages;
    private String publisher;

    public PrintedBook(String title,String author,int yearPublished,int numberOfPages,String publisher){
        super(title,author,yearPublished);
        this.numberOfPages=numberOfPages;
        this.publisher=publisher;
    }

    public String getBookInfo(){
        return super.getBookInfo()+","+numberOfPages+"pages,Publisher:"+publisher;
    }

    public void printBookDetails(){
        System.out.println(getBookInfo());
    }

    public void bookType(){
        System.out.println("This is a printed book");
    }
}


class Ebook extends Book{
    private double fileSizeMB;
    private String fileFormat;

    public Ebook(String title,String author,int yearPublished,double fileSizeMB,String fileFormat){
        super(title,author,yearPublished);
        this.fileSizeMB=fileSizeMB;
        this.fileFormat=fileFormat;
    }

    public String getBookInfo(){
        return super.getBookInfo()+","+fileSizeMB+"MB Format:"+fileFormat;
    }

    public void printBookDetails(){
        System.out.println(getBookInfo());
    }

    public void bookType(){
        System.out.println("This is an Ebook");
    }
}



public class Main{
    public static void main(String[] args){
        PrintedBook printedBook=new PrintedBook("Jamilya", "Ch. Aitmatov", 1958, 316, "Kyrgyzstan");
        Ebook ebook = new Ebook("Groza", "A. Ostrovsky", 1859, 1.5, "PDF");


        printedBook.printBookDetails();
        printedBook.bookType();
        System.out.println();

        ebook.printBookDetails();
        ebook.bookType();
        }
    }
