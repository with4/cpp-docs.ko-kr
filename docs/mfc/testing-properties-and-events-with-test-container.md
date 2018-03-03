---
title: "속성 및 이벤트 테스트 컨테이너와 테스트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- testing, test containers
- tstcon32.exe
- debugging ActiveX controls
- test container
- ActiveX Control Test Container
- ActiveX controls [MFC], testing
- properties [MFC], testing
ms.assetid: 626867cf-fe53-4c30-8973-55bb93ef3917
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 381f4e421b63b2ba48fe649a30e5bf7648b50d27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="testing-properties-and-events-with-test-container"></a>테스트 컨테이너로 속성 및 이벤트 테스트
Visual c + +에서 제공 되는 테스트 컨테이너 응용 프로그램은 ActiveX 컨트롤 컨테이너를 사용 하 여 테스트 및 ActiveX 컨트롤을 디버깅 합니다. 테스트 컨테이너의 속성을 변경, 해당 메서드를 호출 하 고 해당 이벤트를 발생 하 여 컨트롤의 기능을 테스트 하는 컨트롤 개발자를 수 있습니다. 데이터 바인딩 알림 로그를 표시 하 고 또한 ActiveX 컨트롤의 지 속성 기능을 테스트 하기 위한 기능을 제공 하는 테스트 컨테이너: 스트림 또는 하위 속성을 저장,를 다시 로드 및 저장 된 스트림 데이터를 검사 합니다. 이 섹션에서는 테스트 컨테이너의 기본 기능을 사용 하는 방법을 설명 합니다. 추가 정보에 대 한 선택은 **도움말** 테스트 컨테이너를 실행 하는 동안 메뉴.  
  
### <a name="to-access-the-activex-control-test-container"></a>ActiveX Control Test Container를 액세스 하려면  
  
1.  빌드는 [TSTCON 샘플: ActiveX Control Test Container](../visual-cpp-samples.md)합니다.  
  
### <a name="to-test-your-activex-control"></a>ActiveX 컨트롤을 테스트 하려면  
  
1.  에 **편집** 테스트 컨테이너의 메뉴를 클릭 **새 컨트롤 삽입**합니다.  
  
2.  에 **컨트롤 삽입** 상자 원하는 컨트롤을 선택 하 고 클릭 **확인**합니다. 컨트롤은 컨트롤 컨테이너에 표시 됩니다.  
  
    > [!NOTE]
    >  컨트롤에 나열 되지 않은 경우는 **컨트롤 삽입** 대화 상자에서 사용 하 여 등록 되었는지 확인는 **컨트롤 등록** 명령을 **파일** 테스트의 메뉴 컨테이너입니다.  
  
 이 시점에서 컨트롤의 속성 또는 이벤트를 테스트할 수 있습니다.  
  
#### <a name="to-test-properties"></a>속성을 테스트 하려면  
  
1.  에 **제어** 메뉴를 클릭 하 여 **메서드 호출**합니다.  
  
2.  에 **메서드 이름** 드롭 다운 목록에서 테스트 하려는 속성에 대 한 PropPut 방법을 선택 합니다.  
  
3.  수정 된 **매개 변수 값** 또는 **매개 변수 형식** 에서 클릭 하 고는 **값 설정** 단추 합니다.  
  
4.  클릭 **Invoke** 개체에 새 값을 적용 합니다.  
  
     이제는 속성의 새 값을 포함합니다.  
  
#### <a name="to-test-events-and-specify-the-destination-of-event-information"></a>에 이벤트 정보 대상 지정 및 이벤트를 테스트 합니다.  
  
1.  에 **옵션** 메뉴를 클릭 하 여 **로깅**합니다.  
  
2.  이벤트 정보 대상을 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [방법: ActiveX 컨트롤 디버그](/visualstudio/debugger/how-to-debug-an-activex-control)

