---
title: ". 링커 입력으로 사용 하는 Obj 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
ms.assetid: 3028e423-8b10-4972-8eb4-6e9ae58f0a26
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ca8346f9ff29d097450eda4d8bfbfee7f7a3f522
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="obj-files-as-linker-input"></a>링커 입력 파일로 사용하는 .Obj 파일
링커 도구 (링크입니다. EXE).obj 파일에 일반 COFF 개체 파일 형식 ()을 허용 합니다.  
  
## <a name="remarks"></a>설명  
 Microsoft 공용 개체 파일 형식 정의 하는 다운로드 가능한 문서를 제공 합니다. 자세한 내용은 8.1 이상 버전을 다운로드는 [이식 가능한 실행 파일 및 공용 개체 파일 형식 사양을](http://go.microsoft.com/fwlink/?LinkId=93292)합니다.  
  
## <a name="unicode-support"></a>유니코드 지원  
 Visual Studio 2005 이상에서는 Microsoft Visual c + + 컴파일러는 ISO/IEC C 및 c + + 표준에 정의 된 대로 식별자에 유니코드 문자를 지원 합니다. 이전 버전의 컴파일러는 식별자에 ASCII 문자만 지원. 함수, 클래스 및 정적 변수 이름에 유니코드를 지원 하기 위해 컴파일러 및 링커에서의 유니코드 utf-8 인코딩을 사용 COFF 기호.obj 파일에 대 한 합니다. Utf-8 인코딩을 위쪽 이전 버전의 Visual Studio에서 사용 하는 ASCII 인코딩을 호환 됩니다.  
  
 컴파일러 및 링커에서의 하는 방법에 대 한 자세한 내용은 참조 [컴파일러 및 링커에서의 유니코드 지원](../../build/reference/unicode-support-in-the-compiler-and-linker.md)합니다. 유니코드 표준에 대 한 자세한 내용은 참조는 [유니코드](http://go.microsoft.com/fwlink/?LinkId=37123) 조직입니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINK 입력된 파일](../../build/reference/link-input-files.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [유니코드 지원](../../text/support-for-unicode.md)   
 [컴파일러 및 링커에서의 유니코드 지원](../../build/reference/unicode-support-in-the-compiler-and-linker.md)   
 [유니코드 표준](http://go.microsoft.com/fwlink/?LinkId=37123)   
 [공용 개체 파일 형식 사양](http://go.microsoft.com/fwlink/?LinkId=93292)