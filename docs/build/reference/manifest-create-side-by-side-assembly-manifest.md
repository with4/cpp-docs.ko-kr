---
title: "/MANIFEST(side-by-side 어셈블리 매니페스트 만들기) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.GenerateManifest"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFEST 링커 옵션"
  - "MANIFEST 링커 옵션"
  - "-MANIFEST 링커 옵션"
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# /MANIFEST(side-by-side 어셈블리 매니페스트 만들기)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MANIFEST[:{EMBED[,ID=#]|NO}]  
```  
  
## 설명  
 \/MANIFEST는 링커가 side\-by\-side 매니페스트 파일을 만들도록 지정합니다.  매니페스트 파일에 대한 자세한 내용은 [Manifest Files Reference](http://msdn.microsoft.com/library/aa375632)를 참조하십시오.  
  
 기본값은 \/MANIFEST입니다.  
  
 \/MANIFEST:EMBED 옵션은 링커가 manifest파일을 type RT\_MANIFEST의 자료로서 embed하도록 지정합니다.  선택적인 `ID` 변수는 manifest를 위해 사용할 리소스 ID 입니다.  실행할 파일로서 1의 값을 사용하세요.  DLL을 위해 2의 값을 사용해서 개인 종속성들을 지정하세요.  만일 `ID` 변수가 지정되지 않았다면 기본 값은 2이고 \/DLL 옵션이 설정되었거나\/다른 경우, 기본 값은 1입니다.  
  
 [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)]부터 실행 파일의 매니페스트 파일에는 UAC\(사용자 계정 컨트롤\) 정보를 지정하는 섹션이 들어 있습니다.  \/MANIFEST를 지정했지만 [\/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md) 나 [\/DLL](../../build/reference/dll-build-a-dll.md)가 지정되지 않으면 매니페스트에 UAC 수준이 *asInvoker* 로 설정된 기본 UAC 조각으로 삽입됩니다.  UAC 수준에 대한 자세한 내용은 [\/MANIFESTUAC\(매니페스트에 UAC 정보 포함\)](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md)를 참조하십시오.  
  
 UAC의 기본 동작을 변경하려면 다음 중 하나를 수행합니다:  
  
-   \/MANIFESTUAC 옵션을 지정하고 UAC 수준을 원하는 값으로 설정합니다.  
  
-   또는 매니페스트에 UAC 조각을 생성하지 않으려면 \/MANIFESTUAC:NO 옵션을 지정합니다.  
  
 \/MANIFEST를 지정하지 않아도 [\/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md) 주석을 전달하면 매니페스트 파일이 만들어집니다.  \/MANIFEST:NO를 지정하면 매니페스트 파일이 만들어지지 않습니다.  
  
 \/MANIFEST를 지정하면 매니페스트 파일의 이름은 출력 파일의 이름과 같으나 파일 이름에 .manifest가 추가됩니다.  예를 들어, 출력 파일의 이름이 MyFile.exe이면 매니페스트 파일 이름은 MyFile.exe.manifest 입니다.  \/MANIFESTFILE:*namename*을 지정하는 경우 *name*에 지정한 이름이 매니페스트 파일 이름입니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **링커** 노드를 확장합니다.  
  
4.  **매니페스트 파일** 속성 페이지를 선택합니다.  
  
5.  **매니페스트 생성** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)