---
title: "링커 도구 오류 LNK1104 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1104"
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1104
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename' 파일을 열 수 없습니다.  
  
 도구가 지정된 파일을 열 수 없습니다.  
  
 다음과 같은 가능한 원인을 확인하여 수정하세요.  
  
-   디스크 공간이 부족합니다.  
  
-   파일이 없습니다.  
  
-   프로젝트의 속성 페이지 대화 상자에서 라이브러리를 지정할 때 라이브러리 이름은 공백\(쉼표가 아닌\)으로 구분해야 합니다.  
  
-   파일 이름 또는 경로가 잘못되었습니다.  
  
-   드라이브 지정이 잘못되었습니다.  
  
-   파일 사용 권한이 부족합니다.  
  
-   `filename`의 경로는 260자 이상으로 확장 가능합니다.  
  
-   지정된 파일의 이름이 임시 파일의 링커에 의해 생성된 파일 이름인 `LNKn`인 경우 TMP 환경 변수에 지정된 디렉터리가 없거나 둘 이상의 디렉터리가 TMP 환경 변수에 대해 지정되어 있습니다. TMP 환경 변수에 대해 하나의 디렉터리 경로만 지정해야 합니다.  
  
-   라이브러리 이름에 대해 오류 메시지가 발생하고, 이전 Microsoft Visual C\+\+ 개발 시스템에서 .mak 파일을 최근에 포팅한 경우 라이브러리가 더 이상 유효하지 않을 수 있습니다. 이 경우에는 라이브러리가 여전히 있는지 확인합니다.  
  
-   다른 프로그램에서 파일을 열어서 링커에서 해당 파일에 쓸 수 없습니다.  
  
-   LIB 환경 변수가 잘못되었습니다. LIB 환경 변수를 업데이트하는 방법에 대한 자세한 내용은 [VC\+\+ 디렉터리 속성 페이지](../../ide/vcpp-directories-property-page.md) 항목을 참조하세요. 필요한 라이브러리가 포함된 디렉터리 목록이 여기에 있는지 확인합니다.  
  
 링커는 여러 사례에서 임시 파일을 사용합니다. 충분한 디스크 공간이 있는 경우에도 매우 큰 링크는 주소 공간을 상당 부분 사용하거나 조각화할 수 있습니다.  
  
 아래의 해결 방법을 따라 수정하세요.  
  
-   [\/OPT\(최적화\)](../../build/reference/opt-optimizations.md)를 사용합니다. 전이적 comdat 제거 작업은 모든 개체 파일을 여러 번 읽습니다.  
  
-   Windows XP로 업그레이드합니다.