---
title: "#line 지시문 (C/C++) | Microsoft Docs"
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
  - "#line"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#line 지시문"
  - "line 지시문(#line)"
  - "전처리기, 지시문"
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #line 지시문 (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`#line` 디렉티브는 프리프로세서에게 컴파일러의 내부적으로 저장된 라인 수와 파일 이름을 주어진 라인 수와 파일 이름으로 변경하도록 말합니다.  
  
## 구문  
  
```  
  
#line   
digit-sequence ["filename"]  
```  
  
## 설명  
 컴파일러는 줄 번호와 선택적 파일 이름을 사용하여 컴파일 중에 찾은 오류를 참조합니다.  줄 번호는 일반적으로 현재 입력된 줄을 의미하고, 파일 이름은 현재 입력 파일을 의미합니다.  각 줄이 처리 된 후 줄 번호가 증가합니다.  
  
 *숫자 시퀀스* 값은 모든 정수 상수가 될 수 있습니다.  매크로 교체를 전처리 토큰에 수행할 수는 있지만, 결과는 올바른 구문으로 계산되어야 합니다.  *filename*은 문자의 조합일 수 있으며 큰따옴표\(**" "**\)로 묶어야 합니다.  *filename*을 생략하면 이전 파일 이름이 변경되지 않고 유지됩니다.  
  
 `#line` 지시문을 작성하여 원본 줄 번호와 파일 이름을 변경할 수도 있습니다.  번역가는 사전에 정의되어 있는 마크로 **\_\_FILE\_\_**와 **\_\_LINE\_\_**의 값을 확인하기 위해 줄 번호와 파일 이름을 사용합니다.  매크로를 사용하여 자체 설명 오류 메시지를 프로그램에 텍스트에 삽입할 수 있습니다.  이러한 미리 정의된 매크로에 대한 자세한 내용은 [미리 정의된 매크로](../preprocessor/predefined-macros.md)를 참조하십시오.  
  
 **\_\_FILE\_\_** 매크로는 더블 따옴표\(**" "**\)로 싸인 파일 이름이 콘텐츠로 포함된 문자열을 확장합니다.  
  
 줄 번호와 파일 이름을 변경하면 컴파일러가 이전 값을 무시하고 계속 새 값을 사용하여 처리합니다.  일반적으로 `#line` 디렉티브는 프로그램 생성자가 사용하여 오류 메시지를 발생시켜 생성된 프로그램 대신에 원본 소스 파일을 참조하도록 합니다.  
  
 다음 예제에서는 `#line`, **\_\_LINE\_\_** 및 **\_\_FILE\_\_** 매크로를 보여 줍니다.  
  
 이 문에서는 내부에 저장된 줄 번호가 151로 설정되고 파일 이름은 `copy.c`로 변경됩니다.  
  
```  
#line 151 "copy.c"  
```  
  
 이 예제에서 지정된 "어설션"이 true가 아닐 경우 `ASSERT` 매크로는 사전 정의된 매크로인 **\_\_LINE\_\_** 및 **\_\_FILE\_\_**을 사용하여 소스 파일에 대한 오류 메시지를 인쇄합니다.  
  
```  
#define ASSERT(cond)  
  
if( !(cond) )\  
{printf( "assertion error line %d, file(%s)\n", \  
__LINE__, __FILE__ );}  
```  
  
## 참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)