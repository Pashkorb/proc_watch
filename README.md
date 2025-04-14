# proc_watch

Лёгкий Linux Kernel Module для мониторинга событий `fork()` через tracepoint'ы. Логи доступны через sysfs.

## Возможности

- Логирует события `fork`: имя и PID родителя и ребёнка
- Кольцевой буфер (4KB), доступный через `/sys/kernel/proc_watch/buffer`
- Команды:
  - `clear` — очистить буфер
  - `pause` / `resume` — приостановить / возобновить логирование
- Фильтрация по PID родителя через `pid_filter`

## Установка

```bash
make
sudo insmod proc_watch.ko
```
# SysFS интерфейс
```bash
/sys/kernel/proc_watch/
─ buffer       # чтение логов, команды управления
─ pid_filter   # фильтр по PID
```
