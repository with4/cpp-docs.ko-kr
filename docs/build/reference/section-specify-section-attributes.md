---
title: "/SECTION(섹션 특성 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/section"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SECTION 링커 옵션"
  - "section 특성"
  - "SECTION 링커 옵션"
  - "-SECTION 링커 옵션"
ms.assetid: 92b69d81-e421-462e-b46f-7d0dff9b9d16
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /SECTION(섹션 특성 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SECTION:name,[[!]{DEKPRSW}][,ALIGN=#]  
```  
  
## 설명  
 \/SECTION 옵션은 섹션의 .obj 파일을 컴파일할 때 설정한 특성을 재정의하여 섹션의 특성을 변경합니다.  
  
 PE\(이식 가능한 실행\) 파일의 섹션은 NE\(새 실행\) 파일의 세그먼트 또는 리소스와 거의 같습니다.  섹션에는 코드나 데이터가 포함됩니다.  세그먼트와 달리 섹션은 크기 제한이 없는 연속적인 메모리 블록입니다.  일부 섹션에는 프로그램에서 선언하여 직접 사용하는 코드나 데이터가 포함되어 있으며, 다른 데이터 섹션은 링커와 라이브러리 관리자\(lib.exe\)에서 만들며 이러한 섹션에는 운영 체제에 중요한 정보가 포함되어 있습니다.  NE 파일에 대한 자세한 내용은 기술 자료 문서 "Executable\-File Header Format"\(Q65122\)을 참조하십시오.  기술 자료 문서는 MSDN 라이브러리 또는 [http:\/\/support.microsoft.com](http://support.microsoft.com)에 있습니다.  
  
 콜론\(:\)과 섹션의 *name*을 지정합니다.  *name*은 대\/소문자가 구분됩니다.  
  
 다음 이름은 표준 이름과 충돌되므로 사용하지 마십시오.  예를 들어, .sdata는 RISC 플랫폼에서 사용하고 있습니다.  
  
-   .arch  
  
-   .bss  
  
-   .data  
  
-   .edata  
  
-   .idata  
  
-   .pdata  
  
-   .rdata  
  
-   .reloc  
  
-   .rsrc  
  
-   .sbss  
  
-   .sdata  
  
-   .srdata  
  
-   .text  
  
-   .xdata  
  
 섹션에 대해 하나 이상의 특성을 지정합니다.  아래 나열된 특성 문자는 대\/소문자가 구분되지 않습니다.  섹션에 사용할 모든 특성을 지정해야 합니다. 특성 문자를 생략하면 해당 특성 비트가 해제됩니다.  R, W, 또는 E를 지정하지 않으면 기존의 읽기, 쓰기, 실행 가능 상태가 변경되지 않습니다.  
  
 특성을 부정하려면 특성 문자 앞에 느낌표\(\!\)를 붙입니다.  특성 문자의 의미는 다음과 같습니다.  
  
|문자|특성|의미|  
|--------|--------|--------|  
|E|Execute|해당 섹션을 실행할 수 있습니다.|  
|R|Read|데이터를 읽을 수 있습니다.|  
|W|Write|데이터를 쓸 수 있습니다.|  
|S|Shared|이미지를 로드하는 모든 프로세스에서 해당 섹션을 공유합니다.|  
|D|Discardable|해당 섹션을 무시할 수 있는 것으로 표시합니다.|  
|K|Cacheable|해당 섹션을 캐시할 수 없는 것으로 표시합니다.|  
|P|Pageable|해당 섹션을 페이징할 수 없는 것으로 표시합니다.|  
  
 K와 P는 해당하는 섹션 플래그가 부정적인 의미를 나타낸다는 점에서 독특합니다.  .text 섹션\(\/SECTION:.text,K\)에 이들 중 하나를 지정하는 경우 [\/HEADERS](../../build/reference/headers.md) 옵션을 사용하여 [DUMPBIN](../../build/reference/dumpbin-options.md)을 실행할 때 섹션 플래그에는 차이가 없게 됩니다. 이미 암시적으로 캐시된 상태이기 때문입니다.  기본값을 제거하려면 \/SECTION:.text,\!K를 사용합니다. 그러면 DUMPBIN에서는 "캐시되지 않음"을 포함하여 섹션 특성을 표시합니다.  
  
 E, R, 또는 W가 설정되지 않은 PE 파일의 섹션은 유효하지 않습니다.  
  
 ALIGN*\=\#*을 사용하면 특정 섹션의 맞춤 값을 지정할 수 있습니다.  자세한 내용은 [\/ALIGN](../../build/reference/align-section-alignment.md)을 참조하십시오.  
  
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