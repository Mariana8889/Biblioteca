# Biblioteca
Trabalho POO

/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package etapa1;
 

/**
 *
 * @author W10
 */
class Livros {
    private String nome_livro, autor, genero, sequencia;
    private int codigo, quant;
    
    public Livros(String nl, String a, String g, String seq, int cod, int qt) 
    {
        this.nome_livro = nl;
        this.autor = a;
        this.codigo = cod;
        this.genero = g;
        this.quant = qt;
        this.sequencia = seq;
    }
    
    public void setNome_Livro(String nl) 
    {
        this.nome_livro = nl;
    }
    public String getNome_Livro()
    {
        return nome_livro;
    }
    
    public void setAutor(String a) 
    {
        this.autor = a;
    }
    public String getAutor()
    {
        return autor;
    }
    
    public void setGenero (String g) 
    {
        this.genero = g;
    }
    public String getGenero()
    {
        return genero;
    }
    
    public void setSequencia(String sq) 
    {
        this.sequencia = sq;
    }
    public String getSequencia()
    {
        return sequencia;
    }
        
    public void setCodigo(int cod) 
    {
        this.codigo = cod;
    }
    public int getCodigo()
    {
        return codigo;
    }
    
    public void setQuant(int qt) 
    {
        this.quant = qt;
    }
    public int getQuant()
    {
        return quant;
    }
  
    public String toString(){
     String texto = "INFORMAÇÕES DO LIVRO\n\nCodigo: " + Integer.toString(codigo) + "\nNome: " + this.nome_livro +"\nAutor: " + this.autor + "\nGênero: " + this.genero + "\nQuantidade de cópias: " + Integer.toString(quant) + "\nDuologia/Trilogia/Série: " + this.sequencia;
     return texto;
    }
}
 

class Usuarios {
    private String nome, endereco, cpf, telefone;
    
    public Usuarios(String nome, String endereco, String cpf, String telefone) 
    {
        this.nome = nome;
        this.endereco = endereco;
        this.cpf = cpf;
        this.telefone = telefone;
    }
    
    public void setNome(String n) 
    {
        this.nome = n;
    }
    public String getNome()
    {
        return nome;
    }
    
    public void setEndereco(String e) 
    {
        this.endereco = e;
    }
    public String getEndereco()
    {
        return endereco;
    }
    
    public void setCpf(String c) 
    {
        this.cpf = c;
    }
    public String getCpf()
    {
        return cpf;
    }
    
    public void setTelefone(String tel) 
    {
        this.telefone = tel;
    }
    public String getTelefone()
    {
        return telefone;
    }
    
    public String toString(){
     String texto = "INFORMAÇÕES DO USUÁRIO:\n\nNome: " + this.nome +"\nCPF: " + this.cpf + "\nEndereço: " + this.endereco + "\nTelefone" + this.telefone;  
     return texto;
    }
}
 
class Data{
    int dia, mes, ano;
    int devolução;
    
    public Data(int d, int m, int a){
       dia = d;
       mes = m;
       ano = a;
    }
    
     public String toString(){
        return Integer.toString(dia) + "/" + Integer.toString(mes) + "/" + Integer.toString(ano);
    }
}
 

class Emprestimo {
    private String codigo, cpf;
    private Data data_retorno, data_prazo, data_retirada;
    private Multa mt;
    
    public Emprestimo (String codigo, String cpf, Data data_retirada, Data data_prazo, Data data_retorno, Multa mt)
    {
        this.codigo = codigo;
        this.cpf = cpf;
        this.data_prazo = data_prazo;
        this.data_retirada = data_retirada;
        this.data_retorno = data_retorno;
        this.mt = mt;
    }
    
     public Emprestimo (String codigo, String cpf, Data data_retirada, Data data_prazo)
    {
        this.codigo = codigo;
        this.cpf = cpf;
        this.data_prazo = data_prazo;
        this.data_retirada = data_retirada;
        this.data_retorno = new Data(0,0,0);
        this.mt = new Multa(0,0,0,0,0,0);
    }
    
     public void setCpf(String c) 
    {
        this.cpf = c;
    }
    public String getCpf()
    {
        return cpf;
    }
    
    public void setCodigo(String cod) 
    {
        this.codigo = cod;
    }
    public String getCodigo()
    {
        return codigo;
    }
    
    public void setData_retorno(Data drn) 
    {
        this.data_retorno = drn;
    }
    public Data getData_retorno()
    {
        return data_retorno;
    }
    public void setData_retirada(Data drn) 
    {
        this.data_retirada = drn;
    }
    public Data getData_retirada()
    {
        return data_retirada;
    }
    public void setData_prazo(Data drn) 
    {
        this.data_prazo = drn;
    }
    public Data getData_prazo()
    {
        return data_prazo;
    }
    
     public void setMt(Multa m) 
    {
        this.mt = m;
    }
    public Multa getMt()
    {
        return mt;
    }
      
    public String toString()
    {
  
        return "INFORMAÇÕES DE EMPRÉSTIMO: \n\n Identificador do usuário: " + this.cpf + "\nCódigo do livro: " + this.codigo + "\nData de retirada: " + data_retirada.toString() + "\nData limite de entrega: " + data_prazo.toString() + "\nData da devolução: " + data_retorno.toString() +  mt.toString();
    }    
        
}
 
class Multa{
  int drn, dp, mrn, arn, ap, mp;
  double diastotais = CalMulta(this.drn, this.mrn, this.arn, this.dp, this.mp, this.ap);
    
  public Multa(int drn, int mrn, int arn, int dp, int mp, int ap){
      this.ap = ap;
      this.arn = arn;
      this.mp = mp;
      this.mrn = mrn;
      this.dp = dp;
      this.drn = drn;
  }
  
  public static double CalMulta(int drn, int mrn, int arn, int dp, int mp, int ap){
        int x, c, b, diastot, i;
        int[] dias = {0,31,28,31,30,31,30,31,31,30,31,30,31};
        
         x = mrn - mp;
     if((mp==mrn)&&(ap==arn))
    {
        diastot=drn-dp;
    }
 
     else if (x==1)
    {
        diastot=((dias[mp]-dp)+drn);
    }
 
     else if((ap==arn)&& (x>=2))
    {
        diastot=((dias[mp]-dp)+drn);
 
        for(i=(mp+1);i<mrn;i++)
        {
           diastot=(diastot+dias[i]);
        }
    }
 
    else
    {
        diastot=((dias[mp]-dp)+drn);
 
       for(i=12;i>mp;i--)
       {
           diastot=(diastot+dias[i]);
       }
 
        c=arn-ap;
 
        if(c==1)
        {
            for(i=0;i<mrn;i++)
          {
            diastot=diastot+dias[i];
          }
        }
 
        else
        {
            c=c-1;
 
            for(i=0;i<c;i++)
            {
                for(b=0;b<13;b++)
               {
                  diastot=diastot+dias[b];
               }
            }
 
           for(i=0;i<mrn;i++)
           {
               diastot=diastot+dias[i];
           }
        }
    }
     
        return diastot*2.5;
    }
  
 
  public String toString()
  {
      if (diastotais == 0){
      return "";
      }
      else {
          {
      return "Multa: R$: " + Double.toString(diastotais);
      }
      }
  }
 
}
 

public class Etapa1 {
 
    
        
    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        Livros b1;
        b1 = new Livros("A culpa é das estrelas.", "John Green.", "Romance.","Livro único.", 00001,20);
        System.out.println(b1.toString());
        
        Usuarios u1;
        u1 = new Usuarios ("Louis Tomlinson.","Doncaster.", "15500050656", "32988983759");
        System.out.println(u1.toString());
        
        Emprestimo e1, e2;
        e1 = new Emprestimo ("1", "15500050656", new Data(23,01,2021), new Data(04,02,2021),new Data(06,02,2021), new Multa(06,02,2021,04,02,2021));
        System.out.println(e1.toString());
       
    }
    
}
