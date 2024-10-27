## Inspiration
At the start of our brainstorming, ideas flew left and right as we searched for something that resonated with all of us. Yet, everything we considered either felt too familiar or could be easily achieved with existing tools like OpenAI or Anthropic. While these concepts were interesting, none truly excited us, leaving us at a creative standstill for hours in the early hackathon stages.

Then, inspiration struck: helping children with intellectual disabilities engage with literature by simplifying complex sentences into accessible language. We envisioned an AI-powered platform that could make reading more enjoyable and engaging by tailoring texts to the reader’s comprehension level. As we explored this concept, however, we realized the challenge was deeper than text complexity alone. While children’s books offer visual aids to keep young readers interested, other crucial factors like motivation and engagement also influence a child's willingness to learn, particularly for those with developmental disabilities.

Determined not to abandon this idea we had invested so much in, we adapted our approach to reach a wider audience. Our new goal was to enhance reading comprehension for children and adults alike by harnessing the familiarity and appeal of classic literature. By using AI to simplify these beloved stories to fit diverse reading levels, we could cultivate a deeper understanding and appreciation of timeless works while reinforcing reading skills in a positively engaging way.

## What it does
Our platform offers a gamified experience to help users improve their reading skills. Users can explore a library of books and texts, adjusting the reading difficulty on a scale from 1 to 5—where level 5 reflects the original text, and level 1 provides the simplest version. Ever read Shakespeare and wondered, "What did I just read?" With Readable, users can transform complex texts into accessible versions, enhancing both understanding and literacy.

To encourage progress, we reward users with “bamboo” for consistently reading pages at their chosen level. Users read aloud with our voiceover feature, which assesses reading proficiency through a sophisticated similarity algorithm. Higher difficulty levels earn more bamboo, creating a fun incentive to challenge oneself. The bamboo can be used to feed Paul the Panda, our adorable virtual mascot who grows with each feeding. Paul's growth is saved per user, so readers can see him flourish day by day.

Our primary objective is to ensure that users don’t remain at a basic comprehension level. We want them to start with simpler texts and gradually progress to more challenging material, enhancing their reading skills over time. To incentivize this growth, users will earn bamboo rewards for reading more complex texts, motivating them to tackle increasingly difficult material with confidence and enthusiasm. This approach fosters a continuous learning journey while providing tangible rewards for their efforts.

Looking forward, we aim to partner with various organizations to expand bamboo into a universal rewards system and make Paul the Panda a beloved, global reading companion.

## How we built it
We began by assessing our available tools, including Anthropic API, MongoDB Atlas, and Google Cloud, as well as tools we were already familiar with, such as Python and Next.js. With these in mind, we divided our team across the essential components of a tech stack: front-end, back-end, and middleware. Although each member focused on a specific role, we fostered an environment where collaboration and cross-functional support were encouraged.

On the front-end, we built the platform using Next.js, integrating NextAuth and Google OAuth for streamlined user authentication. The back-end leveraged MongoDB and Python functions, algorithms, and LLM API requests, enabling various functions to connect and interact within a unified database. Our MongoDB setup featured complex schemas and operations that allowed us to use the database as the backbone of the entire system, coordinating data flow across all components. Moreover, the front-end could seamlessly communicate with the database via APIs, displaying key information like book details, user progress, and personalized features, such as a user’s bamboo points and the growth of Paul the Panda. These details, stored in the database, would reflect dynamically in the front-end.

A key component of our platform was the adjustable text complexity feature, controlled by a simple slider in the front-end. This seemingly straightforward control activated a robust back-end workflow: the slider sent requests to MongoDB, which triggered Python scripts interfacing with Anthropic API. These scripts adjusted text complexity based on the user-selected difficulty level, using carefully designed prompts tailored for sentence structure, cohesion, vocabulary, and syntax to generate simplified text at each level. The resulting text was then passed through MongoDB middleware to the front-end, displayed in an accessible eBook format.

With numerous interconnected components, creating and using APIs were indispensable for smooth communication and integration throughout the project. This API-driven architecture facilitated efficient data flow from the back-end to the front-end and vice versa, enabling us to create a cohesive, interactive, and intelligent platform.

## Challenges we ran into
We initially thought setting up API endpoints and coordinating requests between the frontend, database, and backend scripts would be the easiest part of our project. However, it turned out to be a 17-hour task within the 36-hour window. Each error revealed a new challenge, but we kept our resolve. At one point, the entire system collapsed, preventing the site from launching. Despite hours of troubleshooting with no immediate solutions, we persisted, embodying perseverance and resilience—fueled by zero hours of sleep and nine collective cans of C4 energy drinks.

Creating an accurate script to assess user transcription quality was a major challenge. After experimenting with various libraries like NumPy, Gemini, and Anthropic, we determined that a custom-designed Scikit-Learn algorithm offered the best approach for our needs. Through logical reasoning and intense trial and error, we finally designed a robust algorithm that met our requirements.

Integrating Anthropic API presented its own set of hurdles, especially given the specificity required for our prompts. We delved into prompt engineering, refining our queries to generate the precise outputs we needed. The research and iterative testing allowed us to create effective, highly specific prompts. In the final hours, we encountered a critical issue: our voice transcription function stopped working. After two hours of searching for solutions, one team member had an epiphany regarding object aliasing, pinpointing the root cause. This was just one of the many breakthroughs that marked our journey, each making the experience even more valuable.

## Accomplishments we're proud of
While we're proud of building a functioning product within 36 hours, our real pride lies in the journey behind it. Beyond coding and learning new technologies, we discovered each other’s strengths, weaknesses, and personalities. Hackathons aren’t just about product development—they’re about community. Through AI ATL, we became closer friends, stronger engineers, and better people.

At one point, everything failed. The localhost crashed, packages wouldn’t load, login stopped working, and we faced a cascade of cryptic errors. It felt like we’d hit rock bottom and were close to quitting. But we didn’t. We kept pushing, problem-solving, and supporting one another. Overcoming these hurdles became our greatest achievement, showing us the power of resilience and teamwork.

## What we learned
We learned that technical challenges can often be tackled through creative problem-solving and collaboration. For instance, mastering API integration and developing a robust similarity script forced us to think critically and adapt quickly. We became proficient in tools like MongoDB and Scikit-Learn, gaining hands-on experience that enhanced our technical acumen.

On a personal level, the experience highlighted the significance of teamwork in high-pressure situations. When our entire system crashed, we leaned on one another for support and brainstormed solutions, transforming frustration into breakthroughs. We recognized that our diverse strengths complemented each other, enabling us to navigate setbacks with resilience. This hackathon not only sharpened our engineering skills but also deepened our friendships and strengthened our commitment to continuous learning and collaboration.

## What's next for Readable?
We envision a customizable experience for Paul the Panda, allowing users to spend their bamboo on various enhancements, such as accessories and clothing. This personalization will add a fun and engaging layer to the platform.

From a technological standpoint, we aim to develop our own machine learning and deep learning model for text simplification, fine-tuned by our engineers for improved accuracy and effectiveness. Given that text simplification is a relatively untapped area in AI, we aspire to be pioneers in advancing this sector.

A significant goal is to use bamboo as a reward currency, enabling users to exchange it for exciting incentives like gift cards and travel miles. While achieving this will require a robust user base and strategic partnerships, it will provide a compelling reason for users to engage with the platform and enhance their reading skills daily.

We also plan to expand our offering to a mobile app, allowing users to access the same features on the go. This shift will significantly increase our user base and provide a popular alternative, especially with the growing trend of eBooks.

Additionally, we aim to enable users to upload a diverse range of texts—beyond just books, including articles and research papers. This will facilitate a scalable text simplification service, making it accessible to a wider audience.

### MongoDB's Role in Readable
MongoDB was a critical component in the development of Readable, serving as the backbone of our data management and integration processes. Its flexible and scalable database structure allowed us to efficiently store, manage, and retrieve diverse sets of data, which played a crucial role in enabling the seamless functionality of our platform. Here are some of the key ways we utilized MongoDB:

1. **Dynamic Data Storage:**  
   MongoDB’s document-based storage model made it easy to store complex and nested data structures. This allowed us to efficiently manage user data, books, text versions at varying difficulty levels, and even tracking elements like bamboo points and the growth of Paul the Panda. The flexibility of the schema-less design meant we could rapidly iterate and adjust data models as our project evolved during the hackathon.

2. **Efficient Data Retrieval and Querying:**  
   Our platform required real-time updates and retrieval of user-specific information, such as reading progress, bamboo points, and personalized book settings. MongoDB's indexing and aggregation capabilities ensure that our queries were fast and responsive, which was essential to providing a smooth, real-time user experience.

3. **Handling User Authentication and Profiles:**  
   With MongoDB, we efficiently manage user profiles, authentication tokens, and associated reading data. The integration with Google OAuth allowed us to securely store and access user information, enabling features like personalized book recommendations, bamboo point tracking, and saved reading levels.

4. **Scalability for Future Growth:**  
   We designed our database architecture with scalability in mind, ensuring that as our platform grows, MongoDB can easily handle increasing user traffic and data volume. Its horizontal scaling feature allows us to distribute data across multiple servers, ensuring consistent performance regardless of the load, which is essential for handling a global user base in the future.

5. **Seamless Integration Across the Tech Stack:**  
   MongoDB served as the glue connecting the front-end, back-end, and middleware components. We utilized APIs to ensure smooth communication between the database and other parts of our system. By storing essential data in MongoDB, such as user progress, simplified text versions, and bamboo rewards, we maintained a cohesive and integrated user experience across all aspects of the platform.

6. **Data Analytics and User Insights:**  
   The aggregation framework in MongoDB allowed us to perform data analysis, enabling us to gain insights into user engagement, reading habits, and platform usage. These insights can be leveraged to make data-driven decisions, improve the platform, and personalize the user experience, such as suggesting reading materials that align with user preferences and skill levels.

Overall, MongoDB was instrumental in building a robust, scalable, and efficient platform that could support complex data structures and real-time interactions. Its flexibility and performance enabled us to implement features seamlessly, allowing us to focus more on enhancing the user experience rather than being bogged down by database limitations.
