---
title: "방법: 명령줄에서 64비트 Visual C++ 도구 집합 활성화 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "64비트 컴파일러[C++], 명령줄 사용법"
  - "64비트 컴파일러[C++], 명령줄에서 도구 집합 활성화"
  - "명령줄[C++], 64비트 컴파일러"
  - "IPF"
  - "IPF, 명령줄 컴파일러"
  - "Itanium[C++]"
  - "Itanium[C++], 명령줄 컴파일러"
  - "x64[C++]"
  - "x64[C++], 명령줄 컴파일러"
ms.assetid: 4da93a19-e20d-4778-902a-5eee9a6a90b5
caps.latest.revision: 30
caps.handback.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 방법: 명령줄에서 64비트 Visual C++ 도구 집합 활성화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+에는 32비트, 64비트 또는 ARM 기반 Windows 운영 체제에서 실행할 수 있는 응용 프로그램을 만드는 데 사용할 수 있는 컴파일러가 포함되어 있습니다.  
  
> [!NOTE]
>  각 Visual C\+\+ 버전에 포함된 특정 도구에 대한 자세한 내용은 [Visual Studio 버전의 Visual C\+\+ 도구 및 템플릿](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md)를 참조하십시오.  
>   
>  Visual Studio IDE를 사용하여 64비트 응용 프로그램을 만드는 방법에 대한 자세한 내용은 [방법: 64비트 플랫폼을 대상으로 한 Visual C\+\+ 프로젝트 구성](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)을 참조하세요.  
  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에는 x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 및 ARM 대상에 대해 x86으로 호스팅되는 32비트, 네이티브 및 크로스 컴파일러가 포함됩니다.  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]를 64 비트 Windows 운영 체제, 32 비트, x86 호스트의 네이티브 및 크로스 컴파일러 및 64 비트에 설치되면 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\-호스트 네이티브 및 크로스 컴파일러는 각 대상\(x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)], 및 ARM\)에 설치됩니다.  각 대상을 위한 32비트 및 64비트 컴파일러는 동일한 코드를 생성하지만 64비트 컴파일러는 미리 컴파일된 헤더 기호 및 전체 프로그램 최적화\([\/GL](../build/reference/gl-whole-program-optimization.md), [\/LTCG](../build/reference/ltcg-link-time-code-generation.md)\) 옵션을 위해 더 많은 메모리를 지원합니다.  32비트 컴파일러를 사용할 때 메모리 제한이 발생하는 경우 64비트 컴파일러를 사용해 보십시오.  
  
 Visual Studio를 64비트 Windows 운영 체제에 설치하면 64비트 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 네이티브 및 x86 크로스 컴파일러에 대한 명령 프롬프트 바로 가기를 추가로 사용할 수 있습니다.  Windows 8에서 이러한 명령 프롬프트에 액세스하려면 **시작** 화면에서 **모든 응용 프로그램**을 엽니다.  설치된 **[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]** 버전에서 **Visual Studio Tools**를 열고 네이티브 도구 또는 크로스 도구 명령 프롬프트 중 하나를 선택합니다.  이전 버전의 Windows에서 **시작**을 선택하고 **모든 프로그램**, **[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]**, **Visual Studio Tools**를 확장한 다음 명령 프롬프트를 선택합니다.  
  
## Vcvarsall.bat  
 컴파일러는 컴파일러 도구 집합을 사용하도록 설정하는 경로 및 환경 변수를 구성하기 위해 명령줄에서 vcvarsall.bat 명령 파일을 실행하여 사용할 수 있습니다.  x86 또는 ARM 플랫폼을 대상으로 하는 64비트 도구 집합을 사용하도록 설정하는 명령 프롬프트 바로 가기는 없으므로, 64비트 도구 집합을 사용하려면 명령 프롬프트 창에서 vcvarsall.bat를 대신 사용합니다.  자세한 내용은 [명령줄 빌드를 위한 경로 및 환경 변수 설정](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)을 참조하십시오.  
  
 다음 단계에서는 x86, x64 및 ARM 플랫폼을 대상으로 64비트 네이티브 도구 집합을 사용하도록 명령 프롬프트를 구성하는 방법을 보여줍니다.  
  
#### 64비트 도구 집합을 사용하기 위해 vcvarsall.bat를 실행하려면  
  
1.  명령 프롬프트에서 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 설치 디렉터리로 변경합니다.  위치는 시스템과 설치한 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에 따라 달라지지만 일반적인 위치는 C:\\Program Files \(x86\)\\Microsoft Visual Studio *버전*\\VC\\입니다. 예를 들어 다음과 같이 입력합니다.  
  
     cd "\\Program Files \(x86\)\\Microsoft Visual Studio 12.0\\VC"  
  
2.  x64 플랫폼을 대상으로 하는 64비트 명령줄 빌드를 위해 이 명령 프롬프트 창을 구성하려면 명령 프롬프트에 다음과 같이 입력합니다.  
  
     `vcvarsall amd64`  
  
3.  x86 플랫폼을 대상으로 하는 64비트 명령줄 빌드를 위해 이 명령 프롬프트 창을 구성하려면 명령 프롬프트에 다음과 같이 입력합니다.  
  
     `vcvarsall amd64_x86`  
  
4.  ARM 플랫폼을 대상으로 하는 64비트 명령줄 빌드를 위해 이 명령 프롬프트 창을 구성하려면 명령 프롬프트에 다음과 같이 입력합니다.  
  
     `vcvarsall amd64_arm`  
  
## 참고 항목  
 [64비트용 프로그램 구성](../build/configuring-programs-for-64-bit-visual-cpp.md)