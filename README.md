# LLamaSharp Android (ARM64)

Библиотека `libllama.so`, оптимизированная для современных Android-процессоров (Snapdragon 8 Elite и аналоги).

## Как использовать в .NET MAUI:

1. Скачайте архив из раздела **Releases**.
2. Распакуйте и положите файл `libllama.so` в ваш проект:
   `Platforms/Android/lib/arm64-v8a/libllama.so`
3. В Visual Studio установите для файла:
   **Build Action: AndroidNativeLibrary**
4. Инициализируйте библиотеку в коде перед использованием:
```csharp
#if ANDROID
LLama.Native.NativeLibraryConfig.Instance
    .WithLibrary("libllama.so")
    .WithLogs(true);
#endif

Особенности сборки:
Поддержка инструкций i8mm и SVE (Snapdragon 8 Elite).

Скомпилировано с флагом GGML_CPU_ALL_VARIANTS=ON.

Не требует установки NuGet-пакетов Backend.Cpu или Backend.Vulkan.
