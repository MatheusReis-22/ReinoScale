import React, { useState } from "react";
import {
  View,
  Text,
  StyleSheet,
  TouchableOpacity,
  TextInput,
  ScrollView,
  Alert,
} from "react-native";

export default function App() {
  const [screen, setScreen] = useState("login");

  const salvarEscala = () => {
    Alert.alert("Sucesso", "Escala cadastrada com sucesso!");
  };

  // LOGIN
  if (screen === "login") {
    return (
      <View style={styles.container}>
        <Text style={styles.logo}>⛪ ReinoScale</Text>
        <Text style={styles.subtitle}>
          Gestão de Escalas e Eventos da Igreja
        </Text>

        <TextInput placeholder="E-mail" style={styles.input} />
        <TextInput placeholder="Senha" secureTextEntry style={styles.input} />

        <TouchableOpacity
          style={styles.button}
          onPress={() => setScreen("home")}
        >
          <Text style={styles.buttonText}>Entrar</Text>
        </TouchableOpacity>
      </View>
    );
  }

  // HOME
  if (screen === "home") {
    return (
      <ScrollView style={styles.scroll}>
        <View style={styles.container}>
          <Text style={styles.title}>🏠 Dashboard</Text>

          <Text style={styles.card}>
            👋 Bem-vindo, Willams Matheus Reis
          </Text>

          <Text style={styles.card}>
            📅 Próximo Culto{"\n"}
            Domingo - 19:00
          </Text>

          <Text style={styles.card}>
            👥 Membros Escalados{"\n"}
            Willams Matheus Reis{"\n"}
            Thiago Reis{"\n"}
            Matheus Reis{"\n"}
            Wilma Reis
          </Text>

          <Text style={styles.card}>
            🔔 Avisos{"\n"}
            • Ensaio sábado às 18h{"\n"}
            • Reunião terça às 19h{"\n"}
            • Congresso de jovens próximo mês
          </Text>

          <TouchableOpacity
            style={styles.button}
            onPress={() => setScreen("escalas")}
          >
            <Text style={styles.buttonText}>📋 Escalas</Text>
          </TouchableOpacity>

          <TouchableOpacity
            style={styles.button}
            onPress={() => setScreen("eventos")}
          >
            <Text style={styles.buttonText}>📅 Eventos</Text>
          </TouchableOpacity>

          <TouchableOpacity
            style={styles.button}
            onPress={() => setScreen("perfil")}
          >
            <Text style={styles.buttonText}>👤 Perfil</Text>
          </TouchableOpacity>

          <TouchableOpacity
            style={styles.button}
            onPress={() => setScreen("membros")}
          >
            <Text style={styles.buttonText}>👥 Membros</Text>
          </TouchableOpacity>

          <TouchableOpacity
            style={styles.button}
            onPress={() => setScreen("avisos")}
          >
            <Text style={styles.buttonText}>📢 Avisos</Text>
          </TouchableOpacity>
        </View>
      </ScrollView>
    );
  }

  // ESCALAS
  if (screen === "escalas") {
    return (
      <ScrollView style={styles.scroll}>
        <View style={styles.container}>
          <Text style={styles.title}>📋 Escalas da Semana</Text>

          <Text style={styles.card}>
            🎵 Louvor{"\n"}• Willams Matheus Reis{"\n"}• Thiago Reis
          </Text>

          <Text style={styles.card}>
            🎤 Vocal{"\n"}• Matheus Reis
          </Text>

          <Text style={styles.card}>
            🙏 Recepção{"\n"}• Wilma Reis
          </Text>

          <Text style={styles.card}>
            🔊 Sonoplastia{"\n"}• Thiago Reis
          </Text>

          <Text style={styles.card}>
            📺 Mídia{"\n"}• Willams Matheus Reis
          </Text>

          <TouchableOpacity
            style={styles.button}
            onPress={() => setScreen("nova")}
          >
            <Text style={styles.buttonText}>➕ Nova Escala</Text>
          </TouchableOpacity>

          <TouchableOpacity
            style={styles.button}
            onPress={() => setScreen("home")}
          >
            <Text style={styles.buttonText}>⬅ Voltar</Text>
          </TouchableOpacity>
        </View>
      </ScrollView>
    );
  }

  // NOVA ESCALA
  if (screen === "nova") {
    return (
      <ScrollView style={styles.scroll}>
        <View style={styles.container}>
          <Text style={styles.title}>➕ Nova Escala</Text>

          <Text style={styles.card}>
            Preencha os dados para cadastrar uma nova escala ministerial.
          </Text>

          <TextInput placeholder="Ministério" style={styles.input} />
          <TextInput placeholder="Responsável" style={styles.input} />
          <TextInput placeholder="Data" style={styles.input} />
          <TextInput placeholder="Horário" style={styles.input} />
          <TextInput placeholder="Observações" style={styles.input} />

          <TouchableOpacity style={styles.button} onPress={salvarEscala}>
            <Text style={styles.buttonText}>Salvar Escala</Text>
          </TouchableOpacity>

          <TouchableOpacity
            style={styles.button}
            onPress={() => setScreen("escalas")}
          >
            <Text style={styles.buttonText}>⬅ Voltar</Text>
          </TouchableOpacity>
        </View>
      </ScrollView>
    );
  }

  // EVENTOS
  if (screen === "eventos") {
    return (
      <View style={styles.container}>
        <Text style={styles.title}>📅 Eventos</Text>

        <Text style={styles.card}>Culto da Família - 08/06/2026</Text>
        <Text style={styles.card}>Vigília de Oração - 15/06/2026</Text>
        <Text style={styles.card}>Congresso de Jovens - 22/06/2026</Text>
        <Text style={styles.card}>Escola Bíblica - 29/06/2026</Text>

        <TouchableOpacity
          style={styles.button}
          onPress={() => setScreen("home")}
        >
          <Text style={styles.buttonText}>⬅ Voltar</Text>
        </TouchableOpacity>
      </View>
    );
  }

  // PERFIL
  if (screen === "perfil") {
    return (
      <View style={styles.container}>
        <Text style={styles.title}>👤 Perfil</Text>

        <Text style={styles.card}>👤 Nome: Willams Matheus Reis</Text>
        <Text style={styles.card}>🎖 Função: Administrador</Text>
        <Text style={styles.card}>⛪ Igreja: Assembleia de Deus</Text>
        <Text style={styles.card}>📧 Email: willams@email.com</Text>
        <Text style={styles.card}>📱 Telefone: (81) 99999-9999</Text>
        <Text style={styles.card}>✅ Status: Ativo</Text>
        <Text style={styles.card}>📅 Último acesso: Hoje</Text>

        <TouchableOpacity
          style={styles.button}
          onPress={() => setScreen("home")}
        >
          <Text style={styles.buttonText}>⬅ Voltar</Text>
        </TouchableOpacity>
      </View>
    );
  }

  // MEMBROS
  if (screen === "membros") {
    return (
      <View style={styles.container}>
        <Text style={styles.title}>👥 Membros</Text>

        <Text style={styles.card}>Willams Matheus Reis - Administrador</Text>
        <Text style={styles.card}>Thiago Reis - Sonoplastia</Text>
        <Text style={styles.card}>Matheus Reis - Vocal</Text>
        <Text style={styles.card}>Wilma Reis - Recepção</Text>
        <Text style={styles.card}>João Reis - Mídia</Text>
        <Text style={styles.card}>Maria Reis - Intercessão</Text>

        <TouchableOpacity
          style={styles.button}
          onPress={() => setScreen("home")}
        >
          <Text style={styles.buttonText}>⬅ Voltar</Text>
        </TouchableOpacity>
      </View>
    );
  }

  // AVISOS
  if (screen === "avisos") {
    return (
      <View style={styles.container}>
        <Text style={styles.title}>📢 Avisos</Text>

        <Text style={styles.card}>🎵 Ensaio geral sábado às 18h</Text>
        <Text style={styles.card}>🙏 Vigília dia 15/06 às 22h</Text>
        <Text style={styles.card}>📖 Escola Bíblica no domingo</Text>
        <Text style={styles.card}>🎉 Congresso de Jovens este mês</Text>

        <TouchableOpacity
          style={styles.button}
          onPress={() => setScreen("home")}
        >
          <Text style={styles.buttonText}>⬅ Voltar</Text>
        </TouchableOpacity>
      </View>
    );
  }

  return null;
}

const styles = StyleSheet.create({
  scroll: {
    flex: 1,
    backgroundColor: "#F4F6F8",
  },

  container: {
    flex: 1,
    justifyContent: "center",
    padding: 20,
    backgroundColor: "#F4F6F8",
  },

  logo: {
    fontSize: 34,
    fontWeight: "bold",
    textAlign: "center",
    color: "#2E7D32",
  },

  subtitle: {
    textAlign: "center",
    marginBottom: 30,
    color: "#666",
  },

  title: {
    fontSize: 28,
    fontWeight: "bold",
    textAlign: "center",
    marginBottom: 20,
  },

  input: {
    backgroundColor: "#FFF",
    borderWidth: 1,
    borderColor: "#DDD",
    padding: 12,
    borderRadius: 10,
    marginBottom: 10,
  },

  card: {
    backgroundColor: "#FFF",
    padding: 15,
    borderRadius: 10,
    marginBottom: 10,
    fontSize: 16,
  },

  button: {
    backgroundColor: "#2E7D32",
    padding: 15,
    borderRadius: 10,
    marginTop: 10,
  },

  buttonText: {
    color: "#FFF",
    textAlign: "center",
    fontWeight: "bold",
  },
});
