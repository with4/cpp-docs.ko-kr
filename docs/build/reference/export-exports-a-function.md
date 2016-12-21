---
title: "/EXPORT(함수 내보내기) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.ExportFunctions"
  - "/export"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/EXPORT 링커 옵션"
  - "EXPORT 링커 옵션"
  - "-EXPORT 링커 옵션"
ms.assetid: 0920fb44-a472-4091-a8e6-73051f494ca0
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /EXPORT(함수 내보내기)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/EXPORT:entryname[,@ordinal[,NONAME]][,DATA]  
```  
  
## 설명  
 이 옵션을 사용하면 다른 프로그램에서 호출할 수 있도록 프로그램에서 함수를 내보낼 수 있습니다.  데이터도 내보낼 수 있습니다.  내보내기는 대개 DLL에서 정의됩니다.  
  
 *entryname*은 호출 프로그램이 사용할 함수 또는 데이터 항목 이름입니다.  `ordinal`은 내보내기 테이블로 1부터 65,535까지의 인덱스를 지정합니다. 사용자가 `ordinal`을 지정하지 않는 경우에는 LIB에서 이 값을 할당합니다.  **NONAME** 키워드는 함수를 *entryname*이 없는 서수로만 내보냅니다.  
  
 **DATA** 키워드는 내보낸 항목을 데이터 항목으로 지정합니다.  클라이언트 프로그램의 데이터 항목은 **extern \_\_declspec\(dllimport\)**을 사용하여 선언해야 합니다.  
  
 정의를 내보내는 데는 다음과 같은 세 가지 방법을 사용합니다\(권장 순서에 따라 나열\).  
  
1.  소스 코드에 [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md) 사용  
  
2.  .def 파일에서 [EXPORTS](../../build/reference/exports.md) 문 사용  
  
3.  LINK 명령에서 \/EXPORT 지정  
  
 동일한 프로그램에서 이 세 가지 방법을 모두 사용할 수 있습니다.  LINK에서는 내보내기가 들어 있는 프로그램을 빌드할 때 해당 빌드에 .exp 파일이 사용되지 않은 경우 가져오기 라이브러리도 만듭니다.  
  
 LINK에서는 데코레이팅된 형식의 식별자를 사용합니다.  컴파일러에서는 .obj 파일을 만들 때 식별자를 데코레이팅합니다.  *entryname*이 데코레이팅되지 않은 형식으로 링커에 지정되는 경우\(소스 코드에 표시\) LINK에서는 일치하는 이름을 찾습니다.  일치하는 이름을 찾을 수 없는 경우에는 오류 메시지가 표시됩니다.  링커에 식별자를 지정해야 할 때 [데코레이팅된 이름](../../build/reference/decorated-names.md) 형식의 식별자를 가져오려면 [DUMPBIN](../../build/reference/dumpbin-reference.md) 도구를 사용합니다.  
  
> [!NOTE]
>  `__cdecl` 또는 `__stdcall`로 선언된 C 식별자의 데코레이팅된 형식은 지정하지 마십시오.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)