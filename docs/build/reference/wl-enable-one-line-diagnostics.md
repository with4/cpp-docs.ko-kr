---
title: "-WL (1 줄 진단 사용) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /wl
dev_langs: C++
helpviewer_keywords:
- -WL compiler option [C++]
- /WL compiler option [C++]
- WL compiler option [C++]
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 48ba6ab05ac596c98c4fa5a95971735c62267a35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="wl-enable-one-line-diagnostics"></a>/WL(1줄 진단 사용)
추가 정보는 오류 또는 경고 메시지를 추가 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/WL  
```  
  
## <a name="remarks"></a>설명  
 오류 및 c + + 컴파일러에서 경고 메시지는 기본적으로 새 줄에 표시 되는 추가 정보도 올 수 있습니다. 명령줄에서 컴파일할 때 오류 또는 경고 메시지에 추가 정보 줄을 추가할 수 있습니다. 로그 파일에 빌드 출력을 캡처하고 다음 해당 로그를 확인 하는 모든 오류 및 경고를 처리 하는 경우이 바람직 할 수도 있습니다. 세미콜론 추가 줄에서 오류 또는 경고 메시지가 구분 됩니다.  
  
 모든 오류 및 경고 메시지 줄 정보의 있어야 합니다. 다음 코드는 추가 정보; 줄에 있는 오류를 생성 합니다. 알려 주고 효과 사용 하는 경우 테스트 **/WL**합니다.  
  
```  
// compiler_option_WL.cpp  
// compile with: /WL  
#include <queue>  
int main() {  
   std::queue<int> q;  
   q.fromthecontinuum();   // C2039  
}  
```  
  
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