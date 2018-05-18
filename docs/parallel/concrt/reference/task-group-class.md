`task_group` 클래스는 대기하거나 취소할 수 있는 병렬 작업 컬렉션을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class task_group;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[task_group](#ctor)|오버로드됨. 새 `task_group` 개체를 생성합니다.|  
|[~ task_group 소멸자](#dtor)|`task_group` 개체를 제거합니다. 호출 하지는 않을 `wait` 또는 `run_and_wait` 소멸자가 실행 전에 예외로 인해 스택 해제의 결과로 소멸자는 실행 되지 않는 경우 개체에서 메서드.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[cancel](#cancel)|이 작업 그룹에서 시작한 작업의 하위 트리를 취소 하려는 시도를 만듭니다. 작업 그룹에 예약 된 모든 작업은 전이적으로 취소 가능한 경우.|  
|[is_canceling](#is_canceling)|작업 그룹 현재 취소 중은 여부 호출자에 게 알립니다. 이 반드시을 나타내지 않는 `cancel` 메서드가 `task_group` 개체 (반드시 반환 하려면이 메서드 `true`). 대/소문자는 것입니다는 `task_group` 인라인으로 실행 개체 및 작업 그룹을 추가로 구성 작업 트리에서 취소 되었습니다. 이 경우 런타임에서 취소가를 통해 이동 하는 미리 확인할 수 `task_group` 개체 `true` 도 반환 됩니다.|  
|[run](#run)|오버로드됨. 작업을 예약는 `task_group` 개체입니다. 경우는 `task_handle` 에 대 한 매개 변수로 전달 `run`의 수명을 관리 하는 것에 대 한 호출자가는 `task_handle` 개체입니다. 매개 변수가 포함 될 수 있는 런타임 내부 힙 할당 함수 개체에 대 한 참조를 사용 하는 메서드의 버전에 대 한 참조를 사용 하는 버전을 사용 하 여 보다 성능이 떨어질는 `task_handle` 개체입니다. `_Placement` 매개 변수를 사용하는 버전은 이 매개 변수로 지정된 위치에서 작업이 실행되도록 합니다.|  
|[run_and_wait](#run_and_wait)|오버로드됨. 사용 하 여 인라인 호출 컨텍스트에서 실행 하는 작업을 예약 된 `task_group` 전체 취소 지원에 대 한 개체입니다. 함수는 다음에 사용 될 때까지 대기는 `task_group` 개체 완료 되거나 취소 되었습니다. 경우는 `task_handle` 에 대 한 매개 변수로 전달 `run_and_wait`의 수명을 관리 하는 것에 대 한 호출자가는 `task_handle` 개체입니다.|  
|[wait](#wait)|에 사용 될 때까지 대기는 `task_group` 개체 완료 되거나 취소 되었습니다.|  
  
## <a name="remarks"></a>설명  
 매우 제한 된 달리 `structured_task_group` 클래스는 `task_group` 클래스는 훨씬 더 일반적인 구문입니다. 모든에 설명 된 제한 없기 [structured_task_group](structured-task-group-class.md)합니다. `task_group` 안전 하 게 개체는 스레드 사용 되 고, 자유 형식 같은 방법으로 사용 될 수 있습니다. 단점은 `task_group` 구문은 수행 하지 않을 수 있습니다 및 `structured_task_group` 적은 양의 작업을 수행 하는 작업에 대 한 작성 합니다.  
  
 자세한 내용은 참조 [작업 병렬 처리](../task-parallelism-concurrency-runtime.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `task_group`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ppl.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="cancel"></a> 취소 

 이 작업 그룹에서 시작한 작업의 하위 트리를 취소 하려는 시도를 만듭니다. 작업 그룹에 예약 된 모든 작업은 전이적으로 취소 가능한 경우.  
  
```  
void cancel();  
```  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [취소](../cancellation-in-the-ppl.md)합니다.  
  
##  <a name="is_canceling"></a> is_canceling 

 작업 그룹 현재 취소 중은 여부 호출자에 게 알립니다. 이 반드시을 나타내지 않는 `cancel` 메서드가 `task_group` 개체 (반드시 반환 하려면이 메서드 `true`). 대/소문자는 것입니다는 `task_group` 인라인으로 실행 개체 및 작업 그룹을 추가로 구성 작업 트리에서 취소 되었습니다. 이 경우 런타임에서 취소가를 통해 이동 하는 미리 확인할 수 `task_group` 개체 `true` 도 반환 됩니다.  
  
```  
bool is_canceling();  
```  
  
### <a name="return-value"></a>반환 값  
 여부를 `task_group` 취소 중가 (또는 곧 되도록 보장) 개체입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [취소](../cancellation-in-the-ppl.md)합니다.  
  
##  <a name="run"></a> 실행 

 작업을 예약는 `task_group` 개체입니다. 경우는 `task_handle` 에 대 한 매개 변수로 전달 `run`의 수명을 관리 하는 것에 대 한 호출자가는 `task_handle` 개체입니다. 매개 변수가 포함 될 수 있는 런타임 내부 힙 할당 함수 개체에 대 한 참조를 사용 하는 메서드의 버전에 대 한 참조를 사용 하는 버전을 사용 하 여 보다 성능이 떨어질는 `task_handle` 개체입니다. `_Placement` 매개 변수를 사용하는 버전은 이 매개 변수로 지정된 위치에서 작업이 실행되도록 합니다.  
  
```  
template<  
   typename _Function  
>  
void run(  
   const _Function& _Func  
);  
  
template<  
   typename _Function  
>  
void run(  
   const _Function& _Func,  
   location& _Placement  
);  
  
template<  
   typename _Function  
>  
void run(  
   task_handle<_Function>& _Task_handle  
);  
  
template<  
   typename _Function  
>  
void run(  
   task_handle<_Function>& _Task_handle,  
   location& _Placement  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Function`  
 작업 핸들의 본문을 실행 하기 위해 호출 될 함수 개체의 형식입니다.  
  
 `_Func`  
 호출할 작업의 본문을 호출 하는 함수입니다. 람다 식 또는 서명 사용 하 여 함수 호출 연산자의 버전을 지 원하는 다른 개체 수도 `void operator()()`합니다.  
  
 `_Placement`  
 `_Func` 매개 변수가 나타내는 작업을 실행해야 할 위치에 대한 참조입니다.  
  
 `_Task_handle`  
 예약 된 작업에 대 한 핸들입니다. 호출자에이 개체의 수명에 대 한 책임을 참고 합니다. 런타임에서 계속 될 때까지 라이브로 `wait` 또는 `run_and_wait` 이 메서드가 호출 된 `task_group` 개체입니다.  
  
### <a name="remarks"></a>설명  
 런타임에서 제공된 된 작업 함수는 호출 함수가 반환 될 수 있는 나중에 실행 되도록 예약 합니다. 이 메서드는 사용 된 [task_handle](task-handle-class.md) 제공된 된 작업 함수의 복사본을 저장 하는 개체입니다. 따라서이 메서드에 전달 하는 함수 개체에서 발생 하는 상태 변경 해당 함수 개체의 복사본에 나타나지 않습니다. 또한 작업 함수에서 반환 될 때까지 포인터에 의해 또는 작업 함수에 참조로 전달 하는 모든 개체의 수명이 계속 유효 해야 합니다.  
  
 경우는 `task_group` 스택 해제 예외에서의 결과로 소멸을 불필요 하는 호출 중 하나로 보장 하기 위해는 `wait` 또는 `run_and_wait` 메서드. 이 경우 소멸자가 적절 하 게 취소 되며 나타내는 작업에 대 한 대기는 `_Task_handle` 매개 변수를 완료 합니다.  
  
 메서드에서 throw는 [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) 태스크가 처리 하는 경우 예외에서 제공 된 `_Task_handle` 매개 변수를 통해 작업 그룹 개체에 이미 예약 되어는 `run` 메서드 되어 없습니다 장애가 있는 호출 중 하나로 `wait` 또는 `run_and_wait` 메서드를 해당 작업 그룹입니다.  
  
##  <a name="run_and_wait"></a> run_and_wait 

 사용 하 여 인라인 호출 컨텍스트에서 실행 하는 작업을 예약 된 `task_group` 전체 취소 지원에 대 한 개체입니다. 함수는 다음에 사용 될 때까지 대기는 `task_group` 개체 완료 되거나 취소 되었습니다. 경우는 `task_handle` 에 대 한 매개 변수로 전달 `run_and_wait`의 수명을 관리 하는 것에 대 한 호출자가는 `task_handle` 개체입니다.  
  
```  
template<  
   class _Function  
>  
task_group_status run_and_wait(  
   task_handle<_Function>& _Task_handle  
);  
  
template<  
   class _Function  
>  
task_group_status run_and_wait(  
   const _Function& _Func  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Function`  
 작업의 본문을 실행하기 위해 호출될 함수 개체의 형식입니다.  
  
 `_Task_handle`  
 인라인 호출 컨텍스트에에서 실행 되는 작업에 대 한 핸들입니다. 호출자에이 개체의 수명에 대 한 책임을 참고 합니다. 런타임에서 계속 될 때까지 라이브로 `run_and_wait` 메서드 실행을 완료 합니다.  
  
 `_Func`  
 함수는 작업의 본문을 호출 하기 위해입니다. 람다 식 또는 서명 사용 하 여 함수 호출 연산자의 버전을 지 원하는 다른 개체 수도 `void operator()()`합니다.  
  
### <a name="return-value"></a>반환 값  
 작업과 작업 중 하나에서 throw 되는 예외 또는 명시적인 취소 작업으로 인해 대기 충족 하는지 여부를 나타내는 값 또는 작업 그룹이 취소 되었습니다. 자세한 내용은 참조 [task_group_status](concurrency-namespace-enums.md#task_group_status)합니다.  

  
### <a name="remarks"></a>설명  
 이 예약 된 작업 중 하나 이상을 참고 `task_group` 개체 인라인 호출 컨텍스트에서 실행할 수 있습니다.  
  
 이 예약 된 작업의 하나 이상이 `task_group` 예외를 throw 하는 개체, 런타임에서 이러한 예외를 하나를 선택 하 고 전파에 대 한 호출에서 `run_and_wait` 메서드.  
  
 반환 되는 `run_and_wait` 메서드를 한 `task_group` 개체를 런타임에 재사용할 수 있는 빈 상태로 개체를 다시 설정 합니다. 경우 여기에 여기서는 `task_group` 개체가 취소 되었습니다.  
  
 두이 방법 중 하나를 호출 해야 실행 비 예외 경로 또는 `wait` 의 소멸자 보다 먼저 메서드는 `task_group` 실행 합니다.  
  
##  <a name="ctor"></a> task_group 

 새 `task_group` 개체를 생성합니다.  
  
```  
task_group();  
  
task_group(  
   cancellation_token _CancellationToken  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_CancellationToken`  
 이 작업 그룹에 연결할 취소 토큰입니다. 작업 그룹은 토큰이 취소될 때 취소됩니다.  
  
### <a name="remarks"></a>설명  
 취소 토큰을 사용하는 생성자는 토큰에 연결된 소스가 취소될 때 취소될 `task_group`을 만듭니다. 명시적 취소 토큰을 제공하면 다른 토큰을 사용하거나 토큰을 사용하지 않는 부모 그룹에서의 암시적 취소에 이 작업 그룹이 참여하지 않도록 격리됩니다.  
  
##  <a name="dtor"></a> ~ task_group 

 `task_group` 개체를 제거합니다. 호출 하지는 않을 `wait` 또는 `run_and_wait` 소멸자가 실행 전에 예외로 인해 스택 해제의 결과로 소멸자는 실행 되지 않는 경우 개체에서 메서드.  
  
```  
~task_group();  
```  
  
### <a name="remarks"></a>설명  
 소멸자가 실행 되 고 (예를 들어 스택 해제 되지 않음 예외로 인해) 정상 실행의 결과로 `wait` 나 `run_and_wait` 메서드도 호출 되지 않은, 소멸자 throw 될 수 있습니다는 [missing_wait](missing-wait-class.md) 예외입니다.  
  
##  <a name="wait"></a> 대기 

 에 사용 될 때까지 대기는 `task_group` 개체 완료 되거나 취소 되었습니다.  
  
```  
task_group_status wait();  
```  
  
### <a name="return-value"></a>반환 값  
 작업과 작업 중 하나에서 throw 되는 예외 또는 명시적인 취소 작업으로 인해 대기 충족 하는지 여부를 나타내는 값 또는 작업 그룹이 취소 되었습니다. 자세한 내용은 참조 [task_group_status](concurrency-namespace-enums.md#task_group_status)합니다.  

  
### <a name="remarks"></a>설명  
 이 예약 된 작업 중 하나 이상을 참고 `task_group` 개체 인라인 호출 컨텍스트에서 실행할 수 있습니다.  
  
 이 예약 된 작업의 하나 이상이 `task_group` 예외를 throw 하는 개체, 런타임에서 이러한 예외를 하나를 선택 하 고 전파에 대 한 호출에서 `wait` 메서드.  
  
 호출 `wait` 에 `task_group` 개체가 다시 사용할 수 있는 빈 상태로 다시 설정 합니다. 경우 여기에 여기서는 `task_group` 개체가 취소 되었습니다.  
  
 두이 방법 중 하나를 호출 해야 실행 비 예외 경로 또는 `run_and_wait` 의 소멸자 보다 먼저 메서드는 `task_group` 실행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [structured_task_group 클래스](structured-task-group-class.md)   
 [task_handle 클래스](task-handle-class.md)