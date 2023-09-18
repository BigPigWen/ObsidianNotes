# SpringBoot中的注解
## 启动注解
| 注解 | 描述 |
| -- | -- |
| @SpringBootApplication | 启动SpringBoot应用 |
## 声明bean的注解
| 注解 | 描述 |
| -- | -- |
| @Service | 在service层使用 |
| @Controller | 在controller层使用 |
| @Repository | 在dao层使用 |

## 注入bean
| 注解 | 描述 |
| -- | -- |
| @Autowired | 自动装配bean |

## contorller注解
| 注解 | 描述 |
| -- | -- |
| @Controller | 控制器，处理http请求，返回view |
| @RestController | 控制器，处理http请求，返回json，等于@ResponseBody+@Controller |
| @RequestMapping | 将http请求映射到MVC和REST控制器的处理方法上 |
| @GetMapping | 处理http的get请求，为@RequestMapping(value = "/",method = RequestMethod.GET)的简写 |
| @PostMapping | 处理http的get请求，为@RequestMapping(value = "/",method = RequestMethod.POST)的简写 |

## 事务注解
| 注解 | 描述 |
| -- | -- |
| @Transactional | 开启SpringBoot事务 |