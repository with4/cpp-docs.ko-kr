---
title: "-vmb,-vmg (표시 메서드) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /vmb
- /vmg
dev_langs:
- C++
helpviewer_keywords:
- vmb compiler option [C++]
- -vmg compiler option [C++]
- vmg compiler option [C++]
- -vmb compiler option [C++]
- /vmb compiler option [C++]
- representation method compiler options [C++]
- /vmg compiler option [C++]
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4a9d64f8b1035f731adef79356d24eeb3e4f7ee3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="vmb-vmg-representation-method"></a>/vmb, /vmg(표시 메서드)
컴파일러는 클래스 멤버에 대 한 포인터를 나타내는 데 사용 하는 방법을 선택 합니다.  
  
 사용 하 여 **/vmb** 클래스의 멤버에 대 한 포인터를 선언 하기 전에 클래스 항상 정의 하는 경우.  
  
 사용 하 여 **/vmg** 하는 클래스를 정의 하기 전에 클래스의 멤버에 대 한 포인터를 선언 합니다. 이 이와 같이 서로 참조 하는 서로 다른 두 클래스에 멤버를 정의 하는 경우에 발생할 수 있습니다. 이러한 상호 참조 클래스에 대 한 정의 되기 전에 하나의 클래스를 참조 해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/vmb  
/vmg  
```  
  
## <a name="remarks"></a>설명  
 사용할 수도 있습니다 [pointers_to_members](../../preprocessor/pointers-to-members.md) 또는 [상속 키워드](../../cpp/inheritance-keywords.md) 사용자 코드에 포인터 표현을 지정 합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)