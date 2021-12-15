unit uPrincipal;

interface

uses
  Winapi.Windows, Winapi.Messages, System.SysUtils, System.Variants, System.Classes, Vcl.Graphics,
  Vcl.Controls, Vcl.Forms, Vcl.Dialogs, Vcl.Menus, uDTMConexao, Enter;

type
  TfrmPrincipal = class(TForm)
    mainPrincipal: TMainMenu;
    Cadastro1: TMenuItem;
    Movimentao1: TMenuItem;
    Relatrio1: TMenuItem;
    Cl1: TMenuItem;
    N1: TMenuItem;
    Categoria1: TMenuItem;
    Produto1: TMenuItem;
    N2: TMenuItem;
    menuFechar: TMenuItem;
    Vendas1: TMenuItem;
    Cliente1: TMenuItem;
    N3: TMenuItem;
    N4: TMenuItem;
    N5: TMenuItem;
    VendaporData1: TMenuItem;
    procedure menuFecharClick(Sender: TObject);
    procedure FormCreate(Sender: TObject);
    procedure Categoria1Click(Sender: TObject);
    procedure FormClose(Sender: TObject; var Action: TCloseAction);
  private
    { Private declarations }
    TeclaEnter: TMREnter;
  public
    { Public declarations }
  end;

var
  frmPrincipal: TfrmPrincipal;

implementation

{$R *.dfm}

uses uCadCategorias;


procedure TfrmPrincipal.Categoria1Click(Sender: TObject);
begin
      frmCadCategoria:=TfrmCadCategoria.Create(Self);
      frmCadCategoria.ShowModal;
      frmCadCategoria.Release;
end;

procedure TfrmPrincipal.FormClose(Sender: TObject; var Action: TCloseAction);
begin
    FreeAndNil(TeclaEnter);
    FreeAndNil(dtmPrincipal);
end;

procedure TfrmPrincipal.FormCreate(Sender: TObject); //OnCreate
begin
   dtmPrincipal := TdtmPrincipal.Create(Self);
   with dtmPrincipal.ConexaoDB do begin
     Connected:=True;
     Params.Database:='C:\DB\VENDAS.GDB';
     Params.Password:='masterkey';
     Params.UserName:='sysdba';
     Params.DriverID:='IB';
   end;

   TeclaEnter := TMREnter.Create(Self);
   TeclaEnter.FocusEnabled:=true;
   TeclaEnter.FocusColor:=clInfoBk;
end;

procedure TfrmPrincipal.menuFecharClick(Sender: TObject);
begin
  Close;
end;

end.
