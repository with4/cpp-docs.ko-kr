---
title: "/CLRUNMANAGEDCODECHECK(SupressUnmanagedCodeSecurityAttribute 추가) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/CLRUNMANAGEDCODECHECK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRUNMANAGEDCODECHECK 링커 옵션"
  - "-CLRUNMANAGEDCODECHECK 링커 옵션"
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# /CLRUNMANAGEDCODECHECK(SupressUnmanagedCodeSecurityAttribute 추가)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/CLRUNMANAGEDCODECHECK**는 링커가 관리 코드에서 네이티브 DLL로의 링커 생성 `PInvoke` 호출에 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>를 적용할지 여부를 지정합니다.  
  
## 구문  
  
```  
/CLRUNMANAGEDCODECHECK[:NO]  
```  
  
## 설명  
 기본적으로 링커는 링커 생성 `PInvoke` 호출에 SuppressUnmanagedCodeSecurityAttribute를 적용합니다.  **\/CLRUNMANAGEDCODECHECK**가 적용된 경우 SuppressUnmanagedCodeSecurityAttribute는 적용되지 않습니다.  
  
 링커는 **\/clr** 또는 **\/clr:pure**를 사용하여 컴파일되는 개체에만 이 특성을 추가합니다.  링커는 **\/clr:safe**를 사용하여 컴파일된 개체에는 `PInvoke` 호출을 생성하지 않습니다.  자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하십시오.  
  
 링커가 관리되는 호출자의 참조에 맞는 관리되는 기호를 찾을 수 없지만 참조에 맞는 네이티브 기호를 찾을 수 있는 경우 링커는 `PInvoke` 호출을 생성합니다.  `PInvoke`에 대한 자세한 내용은 [관리 코드에서 네이티브 함수 호출](../../dotnet/calling-native-functions-from-managed-code.md)을 참조하십시오.  
  
 코드에 <xref:System.Security.AllowPartiallyTrustedCallersAttribute>를 사용하는 경우에는 **\/CLRUNMANAGEDCODECHECK**를 명시적으로 설정해야 합니다.  이미지에 SuppressUnmanagedCodeSecurity와 AllowPartiallyTrustedCallers 특성이 모두 있으면 보안 취약점이 생길 수 있습니다.  
  
 SuppressUnmanagedCodeSecurityAttribute를 사용할 때의 관련 사항에 대한 자세한 내용은 [Security Optimizations](http://msdn.microsoft.com/ko-kr/cf255069-d85d-4de3-914a-e4625215a7c0)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **링커** 노드를 확장합니다.  
  
4.  **고급** 속성 페이지를 선택합니다.  
  
5.  **CLR 비관리 코드 검사** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)