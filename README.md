# MinhaAPICompleta - Entidades no formato JSON


public class FornecedorViewModel
{

	public Guid Id { get; set; }

	public string Nome { get; set; }

	public string Documento { get; set; }

	public int TipoFornecedor { get; set; }

	public EnderecoViewModel Endereco { get; set; }

	public bool Ativo { get; set; }
}


public class EnderecoViewModel
{
	public Guid Id { get; set; }

	public string Logradouro { get; set; }

	public string Numero { get; set; }

	public string Complemento { get; set; }

	public string Bairro { get; set; }

	public string Cep { get; set; }

	public string Cidade { get; set; }

	public string Estado { get; set; }

	public Guid FornecedorId { get; set; }

}	

public class ProdutoViewModel
{
	public Guid Id { get; set; }

	public Guid FornecedorId { get; set; }

	public string Nome { get; set; }

	public string Descricao { get; set; }

	public string ImagemUpload { get; set; }

	public string Imagem { get; set; }

	public decimal Valor { get; set; }

	public DateTime DataCadastro { get; set; }

	public bool Ativo { get; set; }

	public string NomeFornecedor { get; set; }
}



# MinhaAPICompleta - Executando a API em SelfHosting

1º Opção   No diretório do projeto DevIO.Api, executar no CMD o comando:
dotnet run --project  DevIO.Api


2º  Opção  Criar um publish com a opção Folder.
No diretório onde foi gerado o publish, abrir com o CMD o diretório e usar o seguinte comando:
dotnet devio.api.dll



# MinhaAPICompleta - Executando Migration no VS apontando para o ambiente de produção

No projeto onde está o contexto de dados:

1.  $env:ASPNETCORE_ENVIRONMENT='Production'
2. update-database -Verbose -Context MeuDbcontext


No projeto onde está o contexto da API:
update-database -Verbose -Context ApplicationDbContext
