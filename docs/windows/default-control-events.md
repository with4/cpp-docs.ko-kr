---
title: 기본 컨트롤 이벤트 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog editor, default control events
- controls [C++], default control events
- events [C++], controls
- dialog box controls, events
ms.assetid: 75556b23-18f5-4390-97a4-2ecad3309741
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a50b0deeb525481afb1da7221689924c41930bff
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874098"
---
# <a name="default-control-events"></a>기본 컨트롤 이벤트
다음 컨트롤 이름 함께 제공 되는 기본 이벤트를 갖습니다.  
  
|컨트롤 이름|기본 이벤트|  
|------------------|-------------------|  
|애니메이션|**ACN_START**|  
|확인란|**BN_CLICKED**|  
|콤보 상자|**CBN_SELCHANGE**|  
|사용자 지정|**TTN_GETDISPINFO**|  
|날짜 시간 선택|**DTN_DATETIMECHANGE**|  
|편집 상자|**EN_CHANGE**|  
|그룹 상자|(해당 없음)|  
|바로 가기 키|**NM_OUTOFMEMORY**|  
|IP 주소|**IPN_FIELDCHANGED**|  
|목록|**LVN_ITEMCHANGE**|  
|목록 상자|**LBN_SELCHANGE**|  
|월 달력|**MCN_SELCHANGE**|  
|그림 컨트롤|(해당 없음)|  
|진행률|**NM_CUSTOMDRAW**|  
|누름 단추|**BN_CLICKED**|  
|라디오 단추|**BN_CLICKED**|  
|서식 있는 편집|**EN_CHANGE**|  
|스크롤 막대|**NM_THEMECHANGED**|  
|슬라이더|**NM_CUSTOMDRAW**|  
|스핀|**UDN_DELTAPOS**|  
|정적 텍스트|(해당 없음)|  
|탭|**TCN_SELCHANGE**|  
|Tree|**TVN_SELCHANGE**|  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자 컨트롤에 대 한 멤버 변수 정의](../windows/defining-member-variables-for-dialog-controls.md)   
 [사용자 인터페이스 개체와 연결 된 메시지 유형](../mfc/reference/message-types-associated-with-user-interface-objects.md)   
 [메시지 처리기 편집](../mfc/reference/editing-a-message-handler.md)   
 [리플 렉 트 된 메시지에 대 한 메시지 처리기 정의](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)   
 [새 컨트롤 클래스 기반의 변수 선언](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)   
 [가상 함수 재정의](../ide/overriding-a-virtual-function-visual-cpp.md)

