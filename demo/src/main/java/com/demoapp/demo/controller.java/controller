@RestController
@RequestMapping("/api/v1/awards")
public class AwardController {
   private final AwardService awardService;

   @Autowired
   public AwardController(AwardService awardService) {
      this.awardService = awardService;
   }

   @GetMapping
   public List<Award> findAll() {
      return awardService.findAll();
   }

   @GetMapping("/{id}")
   public ResponseEntity<Award> findById(@PathVariable Long id) {
      Optional<Award> awardOptional = awardService.findById(id);

      return awardOptional.map(ResponseEntity::ok)
            .orElseGet(() -> ResponseEntity.notFound().build());
   }

   @PostMapping
   public ResponseEntity<Award> save(@RequestBody Award award) {
      Award savedAward = awardService.save(award);

      return ResponseEntity.ok(savedAward);
   }

   @PutMapping("/{id}")
   public ResponseEntity<Award> update(@PathVariable Long id, @RequestBody Award award) {
      Optional<Award> awardOptional = awardService.findById(id);

      if (awardOptional.isPresent()) {
         award.setId(id);
         Award updatedAward = awardService.save(award);

         return ResponseEntity.ok(updatedAward);
      } else {
         return ResponseEntity.notFound().build();
      }
   }

   @DeleteMapping("/{id}")
   public ResponseEntity<Void> deleteById(@PathVariable Long id) {
      Optional<Award> awardOptional = awardService.findById(id);

      if (awardOptional.isPresent()) {
         awardService.deleteById(id);

         return ResponseEntity.ok().build();
      } else {
         return ResponseEntity.notFound().build();
      }
   }
}
