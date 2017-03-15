---
title: "스타일 편집 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ES_READONLY
- ES_WANTRETURN
- ES_UPPERCASE
- ES_NUMBER
- ES_AUTOHSCROLL
- ES_LOWERCASE
- ES_RIGHT
- ES_MULTILINE
- ES_PASSWORD
- ES_NOHIDESEL
- ES_OEMCONVERT
- ES_LEFT
- ES_CENTER
dev_langs:
- C++
helpviewer_keywords:
- ES_WANTRETURN constant
- edit styles [MFC]
- ES_RIGHT constant
- ES_READONLY constant
- ES_PASSWORD constant
- ES_MULTILINE constant
- ES_LEFT constant
- ES_AUTOVSCROLL constant
- ES_OEMCONVERT constant
- ES_LOWERCASE constant
- ES_NUMBER constant
- ES_UPPERCASE constant
- ES_NOHIDESEL constant
- ES_AUTOHSCROLL constant
- ES_CENTER constant
ms.assetid: e6291dd6-f2cb-4ce2-ac31-32272526625c
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 275e0d2dede038bdbe9061bc8051408442aa70bf
ms.lasthandoff: 02/24/2017

---
# <a name="edit-styles"></a>편집 스타일
-   **ES_AUTOHSCROLL** 줄의 끝에 문자를 입력 하는 경우 오른쪽 텍스트를 10 자도 자동 스크롤됩니다. 사용자가 ENTER 키를 누를 때 컨트롤 0 위치로 복원 하는 모든 텍스트를 스크롤합니다.  
  
-   **ES_AUTOVSCROLL** 마지막 줄에서 ENTER를 누를 때 한 페이지 위로 텍스트를 자동으로 스크롤됩니다.  
  
-   **ES_CENTER** 센터 텍스트 한 줄 또는 여러 줄에 컨트롤을 편집 합니다.  
  
-   **ES_LEFT** 편집 컨트롤에서 한 줄 또는 여러 줄 텍스트 왼쪽 맞춤 합니다.  
  
-   **ES_LOWERCASE** 모든 문자를 입력 한 대로 편집 컨트롤에 소문자로 변환 합니다.  
  
-   **ES_MULTILINE** 여러 줄 편집 컨트롤을 지정 합니다. (기본값은 한 줄.) 하는 경우는 **ES_AUTOVSCROLL** 스타일을 지정 하면 편집 컨트롤 최대한 많은 줄을 표시 하 고 ENTER 키를 누를 때 세로로 스크롤합니다. 경우 **ES_AUTOVSCROLL** 는 제공 되지 편집 컨트롤 많은 줄 원으로 표시 가능한 경고음이 줄이 더 이상 표시 될 수 있습니다 때 ENTER를 누르면 됩니다. 하는 경우는 **ES_AUTOHSCROLL** 스타일을 지정 하면 여러 줄 편집 컨트롤 자동으로 컨트롤을 가로로 스크롤합니다 컨트롤의 오른쪽 가장자리를 벗어나면 캐럿 이동 하는 경우. 새 줄을 시작 하려면 사용자 ENTER를 눌러야 합니다. 경우 **ES_AUTOHSCROLL** 은 컨트롤 바꿈하는지 필요한 경우 다음 줄의 시작 부분에 제공 되지; ENTER를 누를 경우에 새 줄 시작 됩니다. 단어 잘림 방지의 위치는 창 크기에 따라 결정 됩니다. 창 크기가 변경 되 면 단어 잘림 방지 위치 변경 내용 및 텍스트 다시 표시 됩니다. 여러 줄 편집 컨트롤에 스크롤 막대가 있을 수 있습니다. 스크롤 막대가 있는 편집 컨트롤 자체 스크롤 막대 메시지를 처리합니다. 스크롤 막대 스크롤 위에서 설명한 것 처럼 사용 하지 않고 컨트롤 편집한 부모 창에서 전송 된 모든 스크롤 메시지를 처리 합니다.  
  
-   **ES_NOHIDESEL** 컨트롤이 입력된 포커스를 잃고 컨트롤이 입력된 포커스를 받을 때 선택 항목 반전 때 편집 컨트롤 선택 영역을 숨기 일반적으로 합니다. 지정 **ES_NOHIDESEL** 이 기본 동작을 삭제 합니다.  
  
-   **ES_NUMBER** 숫자만 편집 컨트롤에 입력할 수 있습니다.  
  
-   **ES_OEMCONVERT** OEM 문자 집합 및 ANSI로 다시 ANSI 문자 집합에서 편집 컨트롤에 입력 된 텍스트 변환 됩니다. 응용 프로그램을 호출 하는 경우 이렇게 하면 적절 한 문자 변환의 `AnsiToOem` Windows 편집 컨트롤에는 ANSI 문자열 OEM 문자로 변환 하는 함수입니다. 이 스타일은 파일 이름을 포함 하는 편집 컨트롤에 가장 유용 합니다.  
  
-   **ES_PASSWORD** 모든 문자가 별표로 표시 됩니다 (**\***) 편집 컨트롤에 입력 한 합니다. 응용 프로그램이 사용할 수는 `SetPasswordChar` 멤버 함수를 표시 되는 문자를 변경 합니다.  
  
-   **ES_READONLY** 사용자 입력 하거나 편집 컨트롤의 텍스트를 편집할 수 없습니다.  
  
-   **ES_RIGHT** 편집 컨트롤을 오른쪽 맞춤 텍스트 한 줄 또는 여러 줄에 있습니다.  
  
-   **ES_UPPERCASE** 모든 문자를 입력 한 대로 편집 컨트롤에 대문자로 변환 합니다.  
  
-   **ES_WANTRETURN** 사용자가 대화 상자에서 여러 줄 편집 컨트롤에 텍스트를 입력 하는 동안 ENTER 키를 누르면 캐리지 리턴 삽입할 수를 지정 합니다. 이 스타일을 하지 않고 ENTER 키가 대화 상자 기본 누름 단추를 누르는 것과 같습니다. 이 스타일 편집 컨트롤을 한 줄에 영향을 주지 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC에서 사용 되는 스타일](../../mfc/reference/styles-used-by-mfc.md)   
 [CEdit::Create](../../mfc/reference/cedit-class.md#create)   
 [편집 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775464)


