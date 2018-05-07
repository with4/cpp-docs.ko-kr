---
title: 메서드 추가 마법사, IDL 특성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.method.idlattrib
dev_langs:
- C++
helpviewer_keywords:
- Add Method Wizard [C++]
- IDL attributes, Add Method Wizard
ms.assetid: f80c3bc1-b515-4d6c-83ee-98c2c21ba902
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a7a1e8fe89f64ad5909e7c1415545e3b3d80196
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="idl-attributes-add-method-wizard"></a>IDL 특성, 메서드 추가 마법사
메서드 추가 마법사의이 페이지를 사용 하 여 메서드에 대 한 인터페이스 정의 (IDL) 언어 설정을 지정 합니다.  
  
 **ID**  
 메서드를 식별 하는 숫자 ID를 설정 합니다. 참조 [id](http://msdn.microsoft.com/library/windows/desktop/aa367040) 에 *MIDL 참조*합니다.  
  
 이 상자 사용자 지정 인터페이스에 대해 사용할 수 없으면 되며 MFC dispinterface에 사용할 수 없습니다.  
  
 **call_as**  
 이 로컬 메서드를 매핑할 수 있는 원격 메서드의 이름을 지정 합니다. 참조 [call_as](http://msdn.microsoft.com/library/windows/desktop/aa366748) 에 *MIDL 참조*합니다.  
  
 MFC dispinterface에 사용할 수 없습니다.  
  
 **helpcontext**  
 사용자는 도움말 파일의이 메서드에 대 한 정보를 볼 수 있는 컨텍스트 ID를 지정 합니다. 참조 [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) 에 *MIDL 참조*합니다.  
  
 MFC dispinterface에 사용할 수 없습니다.  
  
 **helpstring**  
 적용 되는 요소에 설명 하는 데 사용 되는 문자열을 지정 합니다. 기본적으로 설정은 "메서드 *메서드 이름*." 참조 [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) 에 *MIDL 참조*합니다.  
  
 MFC dispinterface에 사용할 수 없습니다.  
  
 **추가 특성**  
 MFC dispinterface에 사용할 수 없습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|**hidden**|메서드에 존재 하지만 하지 사용자 기반 브라우저에 표시할지 나타냅니다. 참조 [숨겨진](http://msdn.microsoft.com/library/windows/desktop/aa366861) 에 *MIDL 참조*합니다.|  
|**소스**|이벤트 원본 메서드의 멤버 임을 나타냅니다. 참조 [소스](http://msdn.microsoft.com/library/windows/desktop/aa367166) 에 *MIDL 참조*합니다.|  
|`local`|메서드가 원격이 아님을 MIDL 컴파일러에 지정 합니다. 참조 [로컬](http://msdn.microsoft.com/library/windows/desktop/aa367071) 에 *MIDL 참조*합니다.|  
|**restricted**|임의로 호출할 수 없습니다 것을 지정 합니다. 참조 [제한](http://msdn.microsoft.com/library/windows/desktop/aa367157) 에 *MIDL 참조*합니다.|  
|**vararg**|메서드가 가변 인수 수 있는지를 지정 합니다. 이를 위해 마지막 인수에는의 안전 배열 이어야 합니다. **VARIANT** 나머지 모든 인수를 포함 하는 형식입니다. 참조 [vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304) 에 *MIDL 참조*합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [메서드 추가](../ide/adding-a-method-visual-cpp.md)   
 [메서드 추가 마법사](../ide/add-method-wizard.md)