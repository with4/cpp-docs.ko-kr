---
title: "일반적인 MBCS 프로그래밍 팁 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mbcs
dev_langs: C++
helpviewer_keywords:
- MBCS [C++], dialog box fonts
- MS Shell Dlg
- MBCS [C++], programming
- dialog boxes [C++], fonts
ms.assetid: 7b541235-f3e5-4af0-b2c2-a0112cd5fbfb
caps.latest.revision: "9"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a09bfb9b30e279e8d0b7696055c1e54ac56bfae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="general-mbcs-programming-advice"></a>일반적인 MBCS 프로그래밍 팁
다음 팁을 사용 합니다.  
  
-   유연성을 사용 하 여 런타임에 매크로 같은 `_tcschr` 및 `_tcscpy` 가능한 경우. 자세한 내용은 참조 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)합니다.  
  
-   C 런타임을 사용 하 여 `_getmbcp` 함수는 현재 코드 페이지에 대 한 정보를 얻을 수 있습니다.  
  
-   문자열 리소스를 다시 사용 하지 마십시오. 대상 언어에 따라 지정 된 문자열로 변환 될 때 의미가 될 수 있습니다. 예를 들어 "File" 응용 프로그램의 주 메뉴 문자열 "File" 대화 상자에서 다르게 변환 될 수 있습니다. 동일한 이름을 가진 둘 이상의 문자열을 사용 해야 할 경우 각각에 대해 다른 문자열 Id를 사용 합니다.  
  
-   MBCS 지원 운영 체제에서 응용 프로그램이 실행 되 고 있는지 찾으려고 할 수 있습니다. 이렇게 하려면; 프로그램을 시작할 때 플래그를 설정 API 호출에 의존 하지 마십시오.  
  
-   대화 상자를 디자인할 때 약 30%를 허용 MBCS 번역에 대 한 정적 텍스트 컨트롤의 끝에 추가 공간이 있습니다.  
  
-   일부 글꼴 모든 시스템에서 사용할 수 없기 때문에 응용 프로그램에 대 한 글꼴을 선택할 때 주의 해야 하 고 합니다. 예를 들어 일본어 버전의 Windows 2000 Helvetica 글꼴을 지원 하지 않습니다.  
  
-   대화 상자에 대 한 글꼴을 선택할 때 사용 하 여 [MS Shell Dlg](http://msdn.microsoft.com/library/windows/desktop/dd374112) MS Sans Serif 또는 Helvetica 대신 합니다. MS Shell Dlg 대화 상자를 만들기 전에 올바른 글꼴로 시스템에 의해 대체 됩니다. MS Shell Dlg를 사용 하 여이 글꼴에 처리 하기 위해 운영 체제의 모든 변경 내용을 자동으로 사용할 수 있는지 확인 합니다. (MFC 바꿉니다 MS Shell Dlg는 DEFAULT_GUI_FONT 또는 시스템 글꼴 Windows 95, Windows 98 및 Windows NT 4에 이러한 시스템 MS Shell Dlg를 올바르게 처리 하지 않습니다.)  
  
-   응용 프로그램을 디자인할 때 문자열 지역화할 수를 결정 합니다. 의문이 있는 경우 임의의 문자열 지역화를 가정 합니다. 따라서 작업만와 지역화할 수 있는 문자열을 혼합 하지 마십시오.  
  
## <a name="see-also"></a>참고 항목  
 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)   
 [포인터 증가 및 감소](../text/incrementing-and-decrementing-pointers.md)