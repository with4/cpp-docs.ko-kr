---
title: "명령줄 빌드를 위한 경로 및 환경 변수 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "include"
  - "Lib"
  - "Path"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe 컴파일러[C++], 환경 변수"
  - "소스 코드 컴파일[C++], 명령줄"
  - "환경 변수[C++]"
  - "환경 변수[C++], CL 컴파일러"
  - "INCLUDE 예약어"
  - "LIB 환경 변수"
  - "LINK 도구[C++], 환경 변수"
  - "LINK 도구[C++], 경로"
  - "PATH 예약어"
  - "VCVARS32.bat 파일"
ms.assetid: 99389528-deb5-43b9-b99a-03c8773ebaf4
caps.latest.revision: 17
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 명령줄 빌드를 위한 경로 및 환경 변수 설정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 명령줄 빌드 도구에는 설치에 맞춰 사용자 지정된 여러 환경 변수가 필요합니다.  설치되어 있으면 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]는 필수 환경 변수를 설정하는 명령 파일을 만든 다음 이미 이러한 변수가 설정되어 있는 명령 프롬프트 창을 시작하는 바로 가기를 만듭니다.  명령줄 도구를 사용하려는 경우 이러한 바로 가기 중 하나를 실행하거나 일반 명령 프롬프트 창을 연 다음 vcvarsall.bat 명령 파일을 실행할 수 있습니다.  
  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 명령줄 도구는 PATH, TMP, INCLUDE, LIB 및 LIBPATH 환경 변수를 사용하고 도구별 환경 변수도 사용할 수 있습니다.  이러한 환경 변수 값은 설치별로 고유하고 제품 업데이트 또는 업그레이드로 인해 변경될 수 있으므로 이러한 변수를 설정하는 대신 vcvarsall.bat 또는 개발자 명령 프롬프트 바로 가기를 사용하는 것이 좋습니다.  컴파일러 및 링커에서 사용하는 특정 환경 변수에 대한 자세한 내용은 [CL 환경 변수](../build/reference/cl-environment-variables.md) 및 [LINK 환경 변수](../build/reference/link-environment-variables.md)를 참조하세요.  
  
> [!NOTE]
>  여러 명령줄 도구 또는 도구 옵션을 사용하려면 관리자 권한이 필요합니다.  이러한 도구 및 도구 옵션을 사용하려면 열려는 명령 프롬프트 창의 바로 가기 메뉴에서 **관리자로 실행** 옵션을 사용하여 명령 프롬프트 창을 여는 것이 좋습니다.  
  
## 명령 프롬프트 바로 가기 사용  
 모든 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 버전에 포함된 개발자 명령 프롬프트 바로 가기는 명령 프롬프트 창을 열고 x86 프로세서를 대상으로 하는 32비트 x86 네이티브 도구 집합을 사용하도록 환경을 설정합니다.  x64 및 ARM 플랫폼을 대상으로 하는 32비트 크로스 컴파일러의 명령 프롬프트 역시 사용할 수 있습니다  시스템 및 설치된 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 버전에 따라 x64 프로세서를 대상으로 하는 64비트 x64 네이티브 도구 집합에 대한 명령 프롬프트 바로 가기와 x86 프로세서를 대상으로 하는 64비트 크로스 컴파일러도 사용할 수 있습니다.  다음 버전의 명령줄 도구 집합은 모든 Visual Studio 버전에서 사용할 수 있습니다.  
  
 x86의 x86  
 이 도구 집합을 사용하여 x86 컴퓨터에 대한 출력 파일을 만듭니다.  x86 컴퓨터에서 네이티브 32비트 프로세스로 실행되고 64비트 Windows 운영 체제에서 WOW64로 실행됩니다.  
  
 x86용 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\([!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 크로스 컴파일러\)  
 이 도구 집합을 사용하여 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]에 대한 출력 파일을 만듭니다.  x86 컴퓨터에서 네이티브 32비트 프로세스로 실행되고 64비트 Windows 운영 체제에서 WOW64로 실행됩니다.  
  
 x86용 ARM\(ARM 크로스 컴파일러\)  
 이 도구 집합을 사용하여 ARM 컴퓨터에 대한 출력 파일을 만듭니다.  x86 컴퓨터에서 네이티브 32비트 프로세스로 실행되고 64비트 Windows 운영 체제에서 WOW64로 실행됩니다.  
  
 다음 명령줄 도구 집합 버전은 64비트 플랫폼에서 사용할 수 있습니다.  
  
 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]의 x86  
 이 도구 집합을 사용하여 x86 컴퓨터에 대한 출력 파일을 만듭니다.  64비트 Windows 운영 체제에서 네이티브 프로세스로 실행됩니다.  
  
 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] On [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]  
 이 도구 집합을 사용하여 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 컴퓨터에 대한 출력 파일을 만듭니다.  64비트 Windows 운영 체제에서 네이티브 프로세스로 실행됩니다.  
  
 x64용 ARM\(ARM 크로스 컴파일러\)  
 이 도구 집합을 사용하여 ARM 컴퓨터에 대한 출력 파일을 만듭니다.  64비트 Windows 운영 체제에서 네이티브 64비트 프로세스로 실행됩니다.  
  
#### 개발자 명령 프롬프트 창을 열려면  
  
1.  Windows 8 시작 화면에서 Visual Studio Tools를 입력합니다.  입력한 내용에 따라 검색 결과가 바뀝니다. **Visual Studio Tools**가 나타나면 선택합니다.  
  
     이전 버전의 Windows에서는 **시작**을 선택한 다음 검색 상자에 Visual Studio Tools를 입력합니다.  검색 결과에 **Visual Studio Tools**가 나타나면 선택합니다.  
  
2.  **Visual Studio Tools** 폴더에서 사용 중인 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 버전에 해당하는 **개발자 명령 프롬프트**를 엽니다.  관리자로 실행하려면 개발자 명령 프롬프트에 대한 바로 가기 메뉴를 연 다음 **관리자로 실행**을 선택합니다.  
  
 개발자 명령 프롬프트는 x86 프로세서를 대상으로 하는 32비트 네이티브 도구 집합을 사용하도록 환경을 설정합니다.  x64 프로세서를 대상으로 하는 32비트 네이티브 도구 집합을 사용하려면 **x64 Cross Tools 명령 프롬프트**를 선택합니다.  ARM 프로세서를 대상으로 하는 32비트 네이티브 도구 집합을 사용하려면 **ARM Cross Tools 명령 프롬프트**를 선택합니다.  x64 프로세서를 대상으로 하는 64비트 네이티브 도구 집합을 사용하려면 **x64 네이티브 도구 명령 프롬프트**를 선택합니다.  
  
## 명령 프롬프트 창에서 vcvarsall.bat 사용  
 일반 명령 프롬프트 창에서 vcvarsall.bat를 실행하면 네이티브 32비트 또는 64비트 컴파일 또는 x86, x64 또는 ARM 프로세서에 대한 크로스 컴파일을 위한 명령줄을 구성하도록 환경 변수를 설정할 수 있습니다.  인수가 제공되지 않은 경우 vcvarsall.bat는 x86 대상에 대해 32비트 네이티브 컴파일러를 사용하도록 환경 변수를 구성합니다.  그러나 모든 컴파일러를 구성하는 데 사용할 수 있습니다.  설치되지 않았거나 빌드 컴퓨터 아키텍처에서 사용할 수 없는 컴파일러 구성을 지정하는 경우 메시지가 표시됩니다.  다음 표에서는 지원되는 인수를 보여 줍니다.  
  
|Vcvarsall.bat 인수|컴파일러|빌드 컴퓨터 아키텍처|출력 아키텍처 빌드|  
|----------------------|----------|-----------------|----------------|  
|x86|x86 32비트 네이티브|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|x86|  
|x86\_amd64|x86용 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 크로스|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|x86\_arm|x86용 ARM 크로스|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|ARM|  
|amd64|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 64비트 네이티브|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|amd64\_x86|x86용 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 크로스|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|x86|  
|amd64\_arm|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]용 ARM 크로스|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|ARM|  
  
 다음 단계에서는 x86 플랫폼을 대상으로 32비트 네이티브 도구 집합을 사용하도록 명령 프롬프트를 구성하는 방법을 보여줍니다.  
  
#### vcvarsall.bat를 실행하려면  
  
1.  명령 프롬프트에서 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 설치 디렉터리로 변경합니다.  위치는 시스템과 설치한 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에 따라 달라지지만 일반적인 위치는 C:\\Program Files \(x86\)\\Microsoft Visual Studio *버전*\\VC\\입니다. 예를 들어 다음과 같이 입력합니다.  
  
     cd "\\Program Files \(x86\)\\Microsoft Visual Studio 12.0\\VC"  
  
2.  32비트 x86 명령줄 빌드를 위해 이 명령 프롬프트 창을 구성하려면 명령 프롬프트에 다음과 같이 입력합니다.  
  
     `vcvarsall x86`  
  
 또한 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에서는 명령줄 환경을 설정하기 위해 vcvars32.bat를 제공합니다.  vcvars32.bat 파일은 32비트 x86 명령줄 빌드가 가능하도록 적절한 환경 변수를 설정하는 것으로 제한됩니다.  이 파일은 `vcvarsall x86` 명령과 동일합니다.  
  
 명령줄 빌드에 [DEVENV](../Topic/Devenv%20Command%20Line%20Switches.md)를 사용하는 경우 **\/useenv** 옵션을 지정하지 않는 한 vcvarsall.bat 또는 vcvars32.bat로 설정된 환경은 빌드에 영향을 미치지 않습니다.  
  
> [!CAUTION]
>  vcvarsall.bat 파일은 컴퓨터별로 다양합니다.  누락되거나 손상된 vcvarsall.bat 파일을 다른 컴퓨터의 파일로 바꾸지 마세요.  누락된 파일을 바꾸려면 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 설치를 다시 실행합니다.  
>   
>  또한 vcvarsall.bat 파일은 버전별로 다릅니다.  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]의 이전 버전이 설치된 컴퓨터에 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]의 최신 버전을 설치한 경우 동일한 명령 프롬프트 창에서 다른 버전의 vcvarsall.bat 또는 vcvars32.bat를 실행하지 마세요.  
  
## 참고 항목  
 [명령줄 빌드](../build/building-on-the-command-line.md)   
 [링크](../build/reference/linking.md)   
 [링커 옵션](../build/reference/linker-options.md)   
 [C\/C\+\+ 프로그램 컴파일](../build/reference/compiling-a-c-cpp-program.md)   
 [컴파일러 옵션](../build/reference/compiler-options.md)