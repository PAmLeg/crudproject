@Service
public class AwardService {
   private final AwardRepository awardRepository;

   @Autowired
   public AwardService(AwardRepository awardRepository) {
      this.awardRepository = awardRepository;
   }

   public List<Award> findAll() {
      return awardRepository.findAll();
   }

   public Optional<Award> findById(Long id) {
      return awardRepository.findById(id);
   }

   public Award save(Award award) {
      return awardRepository.save(award);
   }

   public void deleteById(Long id) {
      awardRepository.deleteById(id);
   }
}
