---
title: "/MANIFESTDEPENDENCY(매니페스트 종속성 지정) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.AdditionalManifestDependencies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFESTDEPENDENCY 링커 옵션"
  - "MANIFESTDEPENDENCY 링커 옵션"
  - "-MANIFESTDEPENDENCY 링커 옵션"
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /MANIFESTDEPENDENCY(매니페스트 종속성 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MANIFESTDEPENDENCY:manifest_dependency  
```  
  
## 설명  
 \/MANIFESTDEPENDENCY를 사용하면 매니페스트 파일의 \<dependency\> 섹션에 배치되는 특성을 지정할 수 있습니다.  
  
 매니페스트 파일을 만드는 방법에 대한 자세한 내용은 [\/MANIFEST\(side\-by\-side 어셈블리 매니페스트 만들기\)](../../build/reference/manifest-create-side-by-side-assembly-manifest.md)를 참조하십시오.  
  
 매니페스트 파일의 \<dependency\> 섹션에 대한 자세한 내용은 [Publisher Configuration Files](http://msdn.microsoft.com/library/aa375682)를 참조하십시오.  
  
 \/MANIFESTDEPENDENCY 정보는 다음 두 가지 방법 중 하나로 링커에 전달할 수 있습니다.  
  
-   명령줄 또는 지시 파일에서 \/MANIFESTDEPENDENCY를 직접 사용합니다.  
  
-   [comment](../../preprocessor/comment-c-cpp.md) pragma를 사용합니다.  
  
 다음 예제에서는 pragma를 통해 전달되는 \/MANIFESTDEPENDENCY를 보여 줍니다.  
  
```  
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")  
```  
  
 그 결과로 매니페스트 파일에 다음과 같은 엔트리가 생성됩니다.  
  
```  
<dependency>  
  <dependentAssembly>  
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />  
  </dependentAssembly>  
</dependency>  
```  
  
 동일한 \/MANIFESTDEPENDENCY 주석을 다음과 같이 명령줄에서 전달할 수도 있습니다.  
  
```  
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"  
```  
  
 링커는 \/MANIFESTDEPENDENCY 주석을 수집하고 중복된 엔트리를 제거한 다음 결과 XML 문자열을 매니페스트 파일에 추가합니다.  링커가 서로 충돌하는 엔트리를 발견하면 매니페스트 파일이 손상되고 응용 프로그램이 시작되지 않습니다. 문제의 원인을 표시하기 위해 엔트리가 이벤트 로그에 추가될 수 있습니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **링커** 노드를 확장합니다.  
  
4.  **매니페스트 파일** 속성 페이지를 선택합니다.  
  
5.  **추가 매니페스트 종속성** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)