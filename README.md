#
Codealpha_ArtificialIntelligenceChatbot

import java.util.HashMap;
import java.util.Scanner;

public class SimpleChatbot {
    private static final HashMap<String, String> knowledgeBase = new HashMap<>();

    static {
        knowledgeBase.put("hello", "Hello. How may I assist you?");
        knowledgeBase.put("hi", "Hi. What information do you require?");
        knowledgeBase.put("name", "This is CodeAlpha Support Bot.");
        knowledgeBase.put("how are you", "The system is operational. Thank you for asking.");
        knowledgeBase.put("internship", "The CodeAlpha internship requires completion of 2 to 3 Java projects for certification eligibility.");
        knowledgeBase.put("task", "Available tasks: 1. Student Grade Tracker, 2. Stock Trading Platform, 3. AI Chatbot, 4. Hotel Reservation System.");
        knowledgeBase.put("submission", "Submit completed projects via the form shared in the official communication channel.");
        knowledgeBase.put("bye", "Session terminated. Best wishes for your internship.");
        knowledgeBase.put("help", "I can provide information regarding the internship, tasks, and submission process.");
    }

    public static String generateResponse(String userInput) {
        String processedInput = userInput.toLowerCase().trim();
        for (String keyword : knowledgeBase.keySet()) {
            if (processedInput.contains(keyword)) {
                return knowledgeBase.get(keyword);
            }
        }
        return "Unable to process the request. Type 'help' for available topics.";
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("CodeAlpha Support Bot Initialized");
        System.out.println("Type 'bye' to terminate the session");
        System.out.println("----------------------------------------");

        while (true) {
            System.out.print("User: ");
            String userInput = scanner.nextLine();

            if (userInput.equalsIgnoreCase("bye")) {
                System.out.println("Bot: " + generateResponse("bye"));
                break;
            }

            String botResponse = generateResponse(userInput);
            System.out.println("Bot: " + botResponse);
        }
        scanner.close();
    }
}
