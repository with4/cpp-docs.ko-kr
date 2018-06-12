---
title: IDL 특성, 메서드 추가 마법사 | Microsoft Docs
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33337771"
---
# <a name="idl-attributes-add-method-wizard"></a>IDL 특성, 메서드 추가 마법사
이 메서드에 대한 IDL(인터페이스 정의 언어) 설정을 지정하려면 이 메서드 추가 마법사 페이지를 사용합니다.  
  
 **ID**  
 메서드를 식별하는 숫자 ID를 설정합니다. *MIDL 참조*에서 [id](http://msdn.microsoft.com/library/windows/desktop/aa367040)를 확인합니다.  
  
 이 상자는 사용자 지정 인터페이스에는 사용할 수 없으며 MFC dispinterface에 사용할 수 없습니다.  
  
 **call_as**  
 이 로컬 메서드를 매핑할 수 있는 원격 메서드의 이름을 지정합니다. *MIDL 참조*에서 [call_as](http://msdn.microsoft.com/library/windows/desktop/aa366748)를 확인합니다.  
  
 MFC dispinterface에는 사용할 수 없습니다.  
  
 **helpcontext**  
 도움말 파일에서 사용자가 이 메서드에 대한 정보를 볼 수 있는 컨텍스트 ID를 지정합니다. *MIDL 참조*에서 [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851)를 확인합니다.  
  
 MFC dispinterface에는 사용할 수 없습니다.  
  
 **helpstring**  
 적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다. 기본적으로 "메서드 *메서드 이름*"으로 설정됩니다. *MIDL 참조*에서 [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856)을 확인합니다.  
  
 MFC dispinterface에는 사용할 수 없습니다.  
  
 **추가 특성**  
 MFC dispinterface에는 사용할 수 없습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|**hidden**|메서드가 존재하지만 사용자 기반 브라우저에는 표시되지 않습니다. *MIDL 참조*에서 [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861)을 확인합니다.|  
|**source**|메서드의 멤버가 이벤트의 소스입니다. *MIDL 참조*에서 [source](http://msdn.microsoft.com/library/windows/desktop/aa367166)를 확인합니다.|  
|`local`|메서드가 원격이 아니라고 MIDL 컴파일러에 지정합니다. *MIDL 참조*에서 [local](http://msdn.microsoft.com/library/windows/desktop/aa367071)을 확인합니다.|  
|**restricted**|메서드를 임의로 호출할 수 없도록 지정합니다. *MIDL 참조*에서 [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157)를 확인합니다.|  
|**vararg**|메서드가 가변 개수의 인수를 사용하도록 지정합니다. 이 작업을 수행하려면 마지막 인수는 나머지 인수를 모두 포함하는 안전한 **VARIANT** 형식의 배열이어야 합니다. *MIDL 참조*에서 [vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304)를 확인합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [메서드 추가](../ide/adding-a-method-visual-cpp.md)   
 [메서드 추가 마법사](../ide/add-method-wizard.md)