from flask import Flask, render_template, request, redirect
import sqlite3

app = Flask(__name__)

def conectar():
    conexao = sqlite3.connect("alunos.db")
    conexao.row_factory = sqlite3.Row
    return conexao

def criar_banco():
    conexao = conectar()
    conexao.execute("""
        CREATE TABLE IF NOT EXISTS alunos (
            id INTEGER PRIMARY KEY AUTOINCREMENT,
            nome TEXT NOT NULL,
            sobrenome TEXT NOT NULL,
            idade INTEGER NOT NULL,
            turma TEXT NOT NULL,
            email TEXT NOT NULL
        )
    """)
    conexao.commit()
    conexao.close()

@app.route("/")
def index():
    return render_template("index.html")

@app.route("/alunos")
def alunos():
    conexao = conectar()
    alunos = conexao.execute("SELECT * FROM alunos").fetchall()
    conexao.close()
    return render_template("alunos.html", alunos=alunos)

@app.route("/cadastrar", methods=["GET", "POST"])
def cadastrar():
    if request.method == "POST":
        nome = request.form["nome"]
        sobrenome = request.form["sobrenome"]
        idade = request.form["idade"]
        turma = request.form["turma"]
        email = request.form["email"]

        conexao = conectar()
        conexao.execute(
            "INSERT INTO alunos (nome, sobrenome, idade, turma, email) VALUES (?, ?, ?, ?, ?)",
            (nome, sobrenome, idade, turma, email)
        )
        conexao.commit()
        conexao.close()

        return redirect("/alunos")

    return render_template("cadastro.html")

@app.route("/editar/<int:id>", methods=["GET", "POST"])
def editar(id):
    conexao = conectar()

    if request.method == "POST":
        nome = request.form["nome"]
        sobrenome = request.form["sobrenome"]
        idade = request.form["idade"]
        turma = request.form["turma"]
        email = request.form["email"]

        conexao.execute(
            "UPDATE alunos SET nome=?, sobrenome=?, idade=?, turma=?, email=? WHERE id=?",
            (nome, sobrenome, idade, turma, email, id)
        )
        conexao.commit()
        conexao.close()

        return redirect("/alunos")

    aluno = conexao.execute(
        "SELECT * FROM alunos WHERE id=?", (id,)
    ).fetchone()

    conexao.close()

    return render_template("editar.html", aluno=aluno)

@app.route("/excluir/<int:id>")
def excluir(id):
    conexao = conectar()
    conexao.execute("DELETE FROM alunos WHERE id=?", (id,))
    conexao.commit()
    conexao.close()

    return redirect("/alunos")

if __name__ == "__main__":
    criar_banco()
    app.run(debug=True)