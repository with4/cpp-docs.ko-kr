---
title: "/ENTRY(진입점 기호) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/entry"
  - "VC.Project.VCLinkerTool.EntryPointSymbol"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ENTRY 링커 옵션"
  - "ENTRY 링커 옵션"
  - "-ENTRY 링커 옵션"
  - "시작 주소"
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ENTRY(진입점 기호)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ENTRY:function  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *함수*  
 .exe 파일이나 DLL의 사용자 정의 시작 주소를 지정하는 함수입니다.  
  
## 설명  
 \/ENTRY 옵션은 진입점 함수를 .exe 파일이나 DLL의 시작 주소로 지정합니다.  
  
 이 함수는 `__stdcall` 호출 규칙으로 정의해야 합니다.  매개 변수 및 반환 값은 프로그램이 콘솔 응용 프로그램인지 Windows 응용 프로그램인지 DLL인지에 따라 달라집니다.   링커에서 진입점을 설정하여 C 런타임 라이브러리가 올바르게 초기화되고 정적 개체에 대한 C\+\+ 생성자가 실행되도록 하는 것이 좋습니다.  
  
 기본적으로 시작 주소는 C 런타임 라이브러리의 함수 이름입니다.  링커에서는 다음 표에서 보여 주는 것처럼 프로그램 특성에 따라 함수를 선택합니다.  
  
|함수 이름|이 함수를 기본값으로 사용하는 프로그램|  
|-----------|---------------------------|  
|**mainCRTStartup**\(또는 **wmainCRTStartup**\)|\/SUBSYSTEM:**CONSOLE**을 사용하는 응용 프로그램. **main**\(또는 **wmain**\)을 호출합니다.|  
|**WinMainCRTStartup**\(또는 **wWinMainCRTStartup**\)|\/SUBSYSTEM:**WINDOWS**를 사용하는 응용 프로그램. `__stdcall`을 사용하여 정의해야 하는 `WinMain`\(또는 **wWinMain**\)을 호출합니다.|  
|**\_DllMainCRTStartup**|DLL. `__stdcall`이 있는 경우 이를 사용하여 정의해야 하는 `DllMain`을 호출합니다.|  
  
 [\/DLL](../../build/reference/dll-build-a-dll.md) 또는 [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) 옵션을 지정하지 않으면 링커에서는 **main** 또는 `WinMain`의 정의 여부에 따라 하위 시스템과 진입점을 선택합니다.  
  
 **main**, `WinMain` 및 `DllMain` 함수는 세 가지 형식의 사용자 정의 진입점입니다.  
  
 관리되는 이미지를 만들 때 \/ENTRY를 사용하여 지정한 함수에는 LPVOID *var1*, DWORD *var2*, LPVOID *var3* 중 한 가지 시그니처가 있어야 합니다.  
  
 DllMain 진입점을 직접 정의하는 방법에 대한 자세한 내용은 [런타임 라이브러리 동작](../../build/run-time-library-behavior.md)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **고급** 속성 페이지를 클릭합니다.  
  
4.  **진입점** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)