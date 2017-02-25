---
title: "/IMPLIB(가져오기 라이브러리 이름 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/implib"
  - "VC.Project.VCLinkerTool.ImportLIbrary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IMPLIB 링커 옵션"
  - "IMPLIB 링커 옵션"
  - "-IMPLIB 링커 옵션"
  - "가져오기 라이브러리, 기본 이름 재정의"
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /IMPLIB(가져오기 라이브러리 이름 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IMPLIB:filename  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 가져오기 라이브러리의 사용자 지정 이름입니다.  기본 이름 대신 사용됩니다.  
  
## 설명  
 \/IMPLIB 옵션을 사용하면 LINK에서 내보내기가 포함된 프로그램을 빌드할 때 만드는 가져오기 라이브러리의 기본 이름을 재정의할 수 있습니다.  기본 이름은 주 출력 파일의 이름과 확장명 .lib로 만들어집니다.  다음 중 하나 이상이 지정된 경우에는 프로그램에 내보내기가 포함된 것입니다.  
  
-   소스 코드에 [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md) 키워드가 있는 경우  
  
-   .def 파일에 [EXPORTS](../../build/reference/exports.md) 문이 있는 경우  
  
-   LINK 명령의 [\/EXPORT](../../build/reference/export-exports-a-function.md) 사양  
  
 LINK에서는 가져오기 라이브러리를 만들지 않는 경우 \/IMPLIB를 무시합니다.  내보내기가 지정되어 있지 않으면 LINK에서는 가져오기 라이브러리를 만들지 않습니다.  빌드할 때 내보내기 파일이 사용되는 경우 LINK에서는 가져오기 라이브러리가 이미 있는 것으로 가정하므로 다시 만들지 않습니다.  가져오기 라이브러리와 내보내기 파일에 대한 자세한 내용은 [LIB 참조](../../build/reference/lib-reference.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **고급** 속성 페이지를 클릭합니다.  
  
4.  **가져오기 라이브러리** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)