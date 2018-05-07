---
title: 이벤트 처리기 마법사 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.eventhandler.overview
dev_langs:
- C++
helpviewer_keywords:
- Event Handler Wizard [C++]
ms.assetid: af8e1835-94b1-4d9a-b353-c519e011d3a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 544ce4cd0f4ed9a7f3592e5ec1691fb3734b8772
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="event-handler-wizard"></a>이벤트 처리기 마법사
이 마법사는 선택한 클래스에 대화 상자 컨트롤에 대 한 이벤트 처리기를 추가합니다. 이벤트 처리기를 추가 하는 경우는 [속성 창](/visualstudio/ide/reference/properties-window), 대화 상자를 구현 하는 클래스에만 추가할 수 있습니다. 참조 [대화 상자 컨트롤에 대 한 이벤트 처리기 추가](../windows/adding-event-handlers-for-dialog-box-controls.md) 자세한 정보에 대 한 합니다.  
  
 **명령 이름**  
 이벤트 처리기를 추가 하는 데는 선택한 컨트롤을 식별 합니다. 이 상자는 사용할 수 없습니다.  
  
 **메시지 유형**  
 선택한 컨트롤에 대 한 현재 가능한 메시지 처리기 목록을 표시합니다.  
  
 **처리기 함수 이름**  
 이벤트를 처리 하기 위해 추가 하는 함수 이름을 표시 합니다. 기본적으로 이름이 메시지 유형 및 "On"에 의해 추가 명령을 기반으로 합니다. 예를 들어 단추에 대 한 호출 `IDC_BUTTON1`, 메시지 유형 `BN_CLICKED` 함수 처리기 이름 표시 `OnBnClickedButton1`합니다.  
  
 **목록 클래스**  
 이벤트 처리기를 추가할 수 있는 사용 가능한 클래스를 표시 합니다. 선택한 대화 상자에 대 한 클래스는 빨간색으로 표시 됩니다.  
  
 **처리기 설명**  
 선택한 항목에 대 한 설명을 제공는 **메시지 유형을** 상자입니다. 이 상자는 사용할 수 없습니다.  
  
 **추가 및 편집**  
 선택한 클래스 또는 개체에 메시지 처리기를 추가 하 고 컨트롤 알림 처리기 코드를 추가할 수 있도록 새 함수에 텍스트 편집기를 엽니다.  
  
 **코드 편집**  
 추가 하거나 컨트롤 알림 처리기 코드를 편집할 수는 텍스트 편집기에서 선택한 기존 함수를 엽니다.  
  
## <a name="see-also"></a>참고 항목  
 [이벤트 처리기 추가](../ide/adding-an-event-handler-visual-cpp.md)