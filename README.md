# Conversor de Euro para Dólar

Este é um aplicativo Android simples que converte valores de Euros para Dólares. 

## Funcionalidades

- Entrada do valor em Euros
- Conversão do valor para Dólares com uma taxa de câmbio fixa
- Exibição do valor convertido

## Pré-requisitos

- Android Studio instalado
- SDK Android configurado

## Instalação

1. Clone este repositório para sua máquina local usando:
    ```sh
    git clone https://github.com/seuusuario/seurepositorio.git
    ```

2. Abra o projeto no Android Studio.

3. Conecte um dispositivo Android ou inicie um emulador.

4. Compile e execute o aplicativo.

## Estrutura do Projeto

conversor-euro-dolar
 - ├── app
 - │ ├── src
 - │ │ ├── main
 - │ │ │ ├── java/com/example/conversoreuroparadolar
 - │ │ │ │ └── MainActivity.kt
 - │ │ │ ├── res
 - │ │ │ │ ├── layout
 - │ │ │ │ │ └── activity_main.xml
 - │ │ │ │ ├── values
 - │ │ │ │ │ └── strings.xml
 - │ │ │ ├── AndroidManifest.xml
 - │ │ └── build.gradle
 - ├── build.gradle
 - └── settings.gradle

kotlin

## Código Principal

Aqui está o código da atividade principal:

    ```kotlin
    package com.example.conversoreuroparadolar
    
    import android.os.Bundle
    import androidx.appcompat.app.AppCompatActivity
    import com.example.conversoreuroparadolar.databinding.ActivityMainBinding
    
    class MainActivity : AppCompatActivity() {
    
        private lateinit var binding: ActivityMainBinding
    
        override fun onCreate(savedInstanceState: Bundle?) {
            super.onCreate(savedInstanceState)
            binding = ActivityMainBinding.inflate(layoutInflater)
            setContentView(binding.root)
    
            binding.buttonConverter.setOnClickListener {
                val euros: Double = binding.editEuro.text.toString().toDouble()
                val dolares = String.format("%.2f", euros * 0.8)
    
                binding.textDolares.text = "${dolares} $"
            }
        }
    }


Configurações do Gradle
Aqui estão as configurações do Gradle para o projeto:

    plugins {
        alias(libs.plugins.android.application)
        alias(libs.plugins.jetbrains.kotlin.android)
    }
    
    android {
        namespace = "com.example.conversoreuroparadolar"
        compileSdk = 34

    defaultConfig {
        applicationId = "com.example.conversoreuroparadolar"
        minSdk = 24
        targetSdk = 34
        versionCode = 1
        versionName = "1.0"

        testInstrumentationRunner = "androidx.test.runner.AndroidJUnitRunner"
    }

    buildTypes {
        release {
            isMinifyEnabled = false
            proguardFiles(
                getDefaultProguardFile("proguard-android-optimize.txt"),
                "proguard-rules.pro"
            )
        }
    }
    compileOptions {
        sourceCompatibility = JavaVersion.VERSION_1_8
        targetCompatibility = JavaVersion.VERSION_1_8
    }
    kotlinOptions {
        jvmTarget = "1.8"
    }
    viewBinding {
        enable = true
    }
    }
    
    dependencies {
        implementation(libs.androidx.core.ktx)
        implementation(libs.androidx.appcompat)
        implementation(libs.material)
        implementation(libs.androidx.activity)
        implementation(libs.androidx.constraintlayout)
        testImplementation(libs.junit)
        androidTestImplementation(libs.androidx.junit)
        androidTestImplementation(libs.androidx.espresso.core)
    }
    Uso
    Insira o valor em Euros no campo de texto.
    Clique no botão "Converter".
    O valor convertido em Dólares será exibido.
